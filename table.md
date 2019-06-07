## 常用函数的描述表格

格式：

```
 名 + 文档链接            | 曰

| `[函数名](对应文档链接)` | 浓缩描述 |
| ------------------------ | -------- |
| `[函数名](对应文档链接)` | 浓缩描述 |
```

注意：表格的第一列，基本都是网址链接，只不过它的 css 格式是代码块。

## 目录

<details>

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [基础](#%E5%9F%BA%E7%A1%80)
- [输出](#%E8%BE%93%E5%87%BA)
- [宏](#%E5%AE%8F)
- [条件编译](#%E6%9D%A1%E4%BB%B6%E7%BC%96%E8%AF%91)
- [属性(Attribute)](#%E5%B1%9E%E6%80%A7attribute)
  - [代码生成](#%E4%BB%A3%E7%A0%81%E7%94%9F%E6%88%90)
  - [测试](#%E6%B5%8B%E8%AF%95)
  - [派生(derive)](#%E6%B4%BE%E7%94%9Fderive)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

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

[write!]: https://doc.rust-lang.org/std/macro.write.html

| [`println!`][main]                                                | 在屏幕上打印文本，`macro(宏)`            |
| ----------------------------------------------------------------- | ---------------------------------------- |
| [`write!(&mut w, "formatted {}", "arguments").unwrap();`][write!] | `assert_eq!(w, b"formatted arguments");` |

## 宏

[assert_eq!]: https://doc.rust-lang.org/std/macro.assert_eq.html

| [`!`][main]                       | 当看到函数名后，跟着符号 `!` 的时候，就意味着调用的是宏，而不是普通函数。 |
| --------------------------------- | ------------------------------------------------------------------------- |
| [`assert_eq!(a, b);`][assert_eq!] | 断言`a/b`相等，用的是`PartialEq`。{还可以自定义 panic 信息}               |

## 条件编译

[cfg]: https://doc.rust-lang.org/reference/conditional-compilation.html#forms-of-conditional-compilation
[cfg_attr]: https://doc.rust-lang.org/reference/conditional-compilation.html#the-cfg_attr-attribute

- `cfg()`对源代码进行条件区分，`true`就有，`false`剔除编译阶段
- `cfg_attr()`对第一参数作为条件，那(后续参数)`true`就有，`false`没有

| [`#[cfg(target_os = "macos")]`][cfg]                             | 只有目标操作系统是 macos，才为`true`                       |
| ---------------------------------------------------------------- | ---------------------------------------------------------- |
| [`#[cfg_attr(feature = "magic", sparkles, crackles)]`][cfg_attr] | 当`feature = "magin"`为`true`，sparkles 与 crackles 会启用 |

## 属性(Attribute)

属性，是 Rust 对各项标记/相关语法形式的统称，看语法：

- （内属性）InnerAttribute：`#![ Attr ]`：apply to the item that the attribute is declared within. (应用 Attr 所定义的项)
- （外属性）OuterAttribute：`#[ Attr ]`：apply to the thing that follows the attribute. (应用 Attr )
- [Rust 内置的属性](https://doc.rust-lang.org/reference/attributes.html#built-in-attributes-index)

### 代码生成

[inline]: https://doc.rust-lang.org/reference/attributes/codegen.html#the-inline-attribute

| [`#[inline]`][inline] | 提示内联代码。{属于编译器优化的配置} |
| --------------------- | ------------------------------------ |


### 测试

[test]: https://doc.rust-lang.org/reference/attributes/testing.html#the-test-attribute
[cfg_test]: https://doc.rust-lang.org/reference/conditional-compilation.html#test

| [`#[test]`][test]          | (函数)作为测试运行             |
| -------------------------- | ------------------------------ |
| [`#[cfg(test)]`][cfg_test] | 备选：通过条件编译达到同样目的 |

- 注意: 测试模式是通过，`rustc --test`命令或是`cargo test`启用的。

### 派生(derive)

[derive]: https://doc.rust-lang.org/reference/attributes/derive.html
[derive-macros]: https://doc.rust-lang.org/reference/procedural-macros.html#derive-macros

| [`#[derive(PartialEq, Clone)]`][derive]          | 为数据结构自动实现(`impl`)，`PartialEq`和`Clone`trait   |
| ------------------------------------------------ | ------------------------------------------------------- |
| [`#[proc_macro_derive(AnswerFn)`][derive-macros] | 定义一个派生宏`AnswerFn`，可以使用`#[derive(AnswerFn)]` |
