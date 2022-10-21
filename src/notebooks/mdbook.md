# mdBook

## Install

> 注意：rust toolchain 需要 x86_64-pc-windows-msvc 版本才能编译成功

```shell
cargo install mdbook
```

## Use

初始化

```shell
# init a book project
mdbook init <name>
# enter project fold
cd .\<name>\
# render a book
mdbook serve --open
```

构建

```shell
# 构建 book
mdbook build
# 
mdbook watch
```
