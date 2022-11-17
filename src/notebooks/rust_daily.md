# Rust daily

## Question & Answer

问题：

> 输入两个类型为 T 的有序数组 `Vec<T>`，比较其中一个数组是否为另一个的子集，返回特定枚举。
>
> 例如：
>
> A:[1,2,3,4,5], B:[1,2,3] -> Enum::Superlist

思路：

1. 先判断数组长度，返回存在空集的情况；
2. 处理两个长度 `>=1` 的数组，使用短的数组 `a` 去匹配长的数组 `b` 中是否存在等于 `a` 的子集；
3. 最后匹配长度相等的情况下，是否相等。

记录：

```rust
pub enum Comparison {
    Equal,
    Sublist,
    Superlist,
    Unequal,
}
pub fn sublist<T: PartialEq>(_first_list: &[T], _second_list: &[T]) -> Comparison {
    if _first_list.is_empty() && _second_list.is_empty() { return Comparison::Equal; }
    if _first_list.is_empty() { return Comparison::Sublist; }
    if _second_list.is_empty() { return Comparison::Superlist; }
    let first_len = _first_list.len();
    let second_len = _second_list.len();
    let (mut a, mut b): (&[T], &[T]);
    if first_len >= second_len {
        (a, b) = (_first_list, _second_list);
    } else {
        (a, b) = (_second_list, _first_list);
    }

    for i in 0..=a.len()-b.len() {
        let c: i32 = a.iter().skip(i)
            .zip(b.iter())
            .map(|(ai, bi)| if ai == bi { 0 } else { 1 })
            .sum();
        if c == 0 {
            if first_len == second_len {
                return Comparison::Equal;
            } else if first_len > second_len {
                return Comparison::Superlist;
            } else if first_len < second_len {
                return Comparison::Sublist;
            }
        } else {
            continue
        }
    }
    Comparison::Unequal
}
```

我没有采用模式匹配的方式进行处理，使用了最简单的`if`进行判断处理存在的情况。而这里采取了一种模式匹配的方式，非常优雅的处理各种情况。以及使用`windows()`函数返回迭代器，使用`any()`函数传入闭包进行比较。

```rust
pub fn sublist<T: Eq>(a: &[T], b: &[T]) -> Comparison {
    use Comparison::*;
    // grace!!!
    // 使用 match 进行模式匹配
    match (a.len(), b.len()) {
        // 两个数组均为空集
        (0, 0) => Equal,
        // 其中一个数组为空集
        (0, _) => Sublist,
        (_, 0) => Superlist,
        // 匹配后加上判断
        (m, n) if m > n => if a.windows(n).any(|v| v == b) {Superlist} else {Unequal},
        (m, n) if m < n => if b.windows(m).any(|v| v == a) {Sublist} else {Unequal},
        // 两个数组长度相等
        (_, _) => if a == b {Equal} else {Unequal},
    }
}
```

`a.len()`返回长度。

可以发现`Vec<T>`是`[T;N]`的高级实现，当函数形参为`&[T]`时，两者都可以作为实参。

`&[T]`是`slice`类型，只要对一个有长度的数据类型进行切片，就是`slice`类型。

其中的`windows(size)`返回一个`Windows`类型的迭代器，这个迭代器的`next()`会从头开始获取所有长度为`size`的`slice`，切片长度小于`size`的切片不会返回。`size`不能为0。

```rust
let slice = ['r', 'u', 's', 't'];
let mut iter = slice.windows(2);
assert_eq!(iter.next().unwrap(), &['r', 'u']);
assert_eq!(iter.next().unwrap(), &['u', 's']);
assert_eq!(iter.next().unwrap(), &['s', 't']);
assert!(iter.next().is_none());
```

`any()`是迭代器中实现的方法。接受一个返回`bool`的闭包，应用于每一个迭代器，只要有一个返回`True`则返回`True`。

```rust
let a = [1, 2, 3];
assert!(a.iter().any(|&x| x > 0));
assert!(!a.iter().any(|&x| x > 5));
```

`slice`实现了`==`特性，所以可以直接使用`&[T]==&[T]`进行判断是否相等。
