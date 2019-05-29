## 常用函数的描述表格

格式：

| 名 + 文档链接            | 曰       |
| ------------------------ | -------- |
| `[函数名](对应文档链接)` | 浓缩描述 |

## 目录

<details>

<!-- START doctoc -->
<!-- END doctoc -->

</details>

按功能/主题分类

## 基础

[main]: https://kaisery.github.io/trpl-zh-cn/ch01-02-hello-world.html#a%E5%88%86%E6%9E%90-rust-%E7%A8%8B%E5%BA%8F
[try]: http://llever.com/rust-by-example-cn/error/multiple_error_types/enter_try.html
[unwrap]: http://llever.com/rust-by-example-cn/error/option_unwrap.html

| [`fn main`][main]    | `main` 函数是一个特殊的函数：在可执行的 Rust 程序中，它总是最先运行的代码                               |
| -------------------- | ------------------------------------------------------------------------------------------------------- |
| [`unwrap()`][unwrap] | `Ok`/`Some`就返回里面的值，`Err`/`None` 就 panic，让程序崩溃                                            |
| [`try!()`][try]      | 语法糖`?`， `Ok`/`Some`就返回里面的值（比如：赋个值什么的）， `Err`/`None` 就将错误值，返回到上层(函数) |

## 输出

| [`println!`][main] | 在屏幕上打印文本，`macro(宏)` |
| ------------------ | ----------------------------- |
|                    |                               |

## 宏

| [`!`][main] | 当看到函数名后，跟着符号 `!` 的时候，就意味着调用的是宏，而不是普通函数。 |
| ----------- | ------------------------------------------------------------------------- |
|             |                                                                           |
