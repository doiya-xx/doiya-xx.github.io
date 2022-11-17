<!-- +++
author: lxmon
create: 2022-10-21
modify: 2022-10-21
tag: [notebook]
+++ -->

# Learning Rust Progress

## List

Reading list：

- ...

Waiting list:

- The Rust Standard Library
- The Rust Reference (Rust 语言规范参考)
- The Rust Cookbook (PS: 各种编程实践)

Books:

- [x] The Rust Programming Language
- [x] mdBook Documentation
- [x] Rust 圣经
- [ ] The Rust Standard Library (标准库)
- [ ] The Rust Reference (Rust 语言规范参考)
- [ ] The Rust Cookbook (PS: 各种编程实践)
- [ ] Rusty Book (Awesome + Cookbook)
- [ ] ...

Articles:

- [x] learning-rust-in-2020
- [ ] ...

Tools:

- [x] mdBook
- [x] Rustlings
- [ ] ...

## Books & Articles

### The Rust Programming Language

Address:

- en: [https://doc.rust-lang.org/book/](https://doc.rust-lang.org/book/)
- zh: [https://www.rustwiki.org.cn/zh-CN/book/](https://www.rustwiki.org.cn/zh-CN/book/)

Date：2022/10/08-2022/10/20

Notebook：[rust.md](./rust.html)

这本书是官方提供的书，中文名称为`Rust 程序设计语言`，出版名为`Rust 权威指南`。我入门Rust阅读的第一本书，印证了Rust学习路线陡峭。其中的`引用借用`、`所有权`，是相比其他有指针语言难以理解，而最后一部分的高级特性是晦涩难懂。但是，作为刚入门，还有很多需要学习的地方，而幸运的Rust社区提供很多好文章，可以继续学习。

### mdBook Documentation

Address:

- en: [https://rust-lang.github.io/mdBook/index.html](https://rust-lang.github.io/mdBook/index.html)
- zh: [https://hellowac.github.io/mdbook_doc/zh-cn/index.html](https://hellowac.github.io/mdbook_doc/zh-cn/index.html)

mdBook 工具指导。mdBook 是一个文档构建工具。

### Rust 圣经

Address: [https://course.rs](https://course.rs)

Date: 2022/10/22

阅读了几章后，发现是 Rust 官方的中文版的个人版，多了一些白话和理解。但是没有更多的解释，例子包括官方的例子和一些自己的例子。或许后面的实战章节会更好一点？后面的多了一些章节深入的探究。生命周期不错。

Date: 2022/10/25

基本把`Rust 圣经`看完了，这本书将中文翻译的内容打散，放在其中的2，3章中，从第三章开始，多了许多作者的理解；

- 第四章讲了Rust中的异步编程，开始拓展；
- 第五章针对容易混淆的地方进行对比，但是很多有还没有完成；
- 第六介绍如何进行测试和使用`Github Actions`；
- 第七章介绍使用`Cargo`；
- 第九章介绍日志；
- 第十章关于Rust实践的介绍；
- 第十一章：这一章是英文书`Learn Rust With Entirely Too Many Linked Lists`的翻译，简述如何通过链表实现栈和队列。从简单的链接开始实现，然后逐渐完善和优化，难度十分大。
- 剩下的内容还没有完成。

接下来，应该是开始实现一些项目，然后一边参考标准库。

### Learn Rust With Entirely Too Many Linked Lists

Address: [Link](https://rust-unofficial.github.io/too-many-lists/)

简述如何使用Rust创建链表，实现栈和队列。

### learning-rust-in-2020

Address:

- en: [learning-rust-in-2020](https://github.com/pretzelhammer/rust-blog/blob/master/posts/learning-rust-in-2020.md)
- zh: [Rust 大佬给初学者的学习建议](https://github.com/rustlang-cn/Rustt/blob/main/Articles/%5B2022-04-02%5D%20Rust%20%E5%A4%A7%E4%BD%AC%E7%BB%99%E5%88%9D%E5%AD%A6%E8%80%85%E7%9A%84%E5%AD%A6%E4%B9%A0%E5%BB%BA%E8%AE%AE.md)

> 摘要
>
> 如果你是一个完完全全的 Rust 小白，想要在一天中尽可能多的学习 Rust，那我推荐你去阅读 fasterthanlime 的《半小时快速了解 Rust》，然后完成 Rustlings 项目中的练习。
>
> 如果你已经学过 Rust 的基本语法，你可以试着做一下 Exercism.io 网站上的 Rust 部分。如果你遇到了问题，你可以在 Google 或者 StackOverflow 上寻求帮助。我推荐你花点时间来简单的阅读和浏览一下《Rust Standard Library Docs》，它是一个很棒的学习资料，里面有一些简单且实用例子去帮助你更好的使用 Rust 的标准库。《Rust by Example》也是一本高质量的参考资料，你可以通过他快速的学习 Rust 的语法和特性。如果你想要更深入的理解 Rust 的某一个概念，那么我推荐你在《The Rust Programming Language》这本书中寻找相关的章节去阅读。尤其推荐在 Exercism.io 上进行练习。在完成每个题目之后，你可以查看其他所有人的题解，可以按点赞数排序来找到通俗易懂并且巧妙的题解。这是一种很棒的学习方式。
>
> 此时，你可能已经是一个高级的初学者，能够找到属于自己的学习路线。但，如果你还需要更多的指导并想要尝试用 Rust 来写一些简单的程序，我推荐你试一着做一下 Advent of Code 2018 Calendar 上的练习。为什么推荐你做 2018 年的题目呢？因为当你做完了这个练习，你可以和 BurntSushi 提供的答案（ BurntSushi's Advent of Code 2018 Rust solutions）进行对比。BurntSushi 写的 Rust 代码整洁、可读性强、通俗易懂。阅读一个有经验的 Rustacean 的代码将会使你受益无穷。

作者从过来人的角度，介绍了学习Rust的一些路线和工具。确实提供了一些帮助。<br>文章的中间还介绍了几个Rust练习场的好坏，以及推荐你去哪里进行练习。<br>原作者库：[pretzelhammer/rust-blog](https://github.com/pretzelhammer/rust-blog)，还有其他一些文章值得阅读。

## Tools

### Rustlings

Address:

- en: [https://github.com/rust-lang/rustlings/](https://github.com/rust-lang/rustlings/)
- zh: [https://github.com/rust-lang-cn/rustlings-cn](https://github.com/rust-lang-cn/rustlings-cn)

Install:

```shell
# find out the latest version at https://github.com/rust-lang/rustlings/releases/latest (on edit 5.2.1)
git clone -b 5.2.1 --depth 1 https://github.com/rust-lang/rustlings
cd rustlings
cargo install --force --path .
```

这个是官方提供的Rust学习工具，提供关于Rust的练习。可以通过命令行下载源，使用`cargo`下载依赖进行使用。通过提供的编译错误，编写解决目标Rust文件的代码。在我阅读完`The Rust Programming Language`后，目前只能解决到`iterator`。其中有些题目过于简单，而有些题目突然难度折跃性暴涨，会使人不知所措。
