# Rust-tour 

「 顾名思义, rust 的旅行, rust路途是颠簸的 」

> 中途可能会下车, [对 Rust 的分析](http://www.yinwang.org/blog-cn/2016/09/18/rust)

[github source](https://github.com/rust-lang/rust)

[中文](./readme.md) | ~~[english](./readme.en.md)~~

---

### rust

> 在这一刻, 写下, 我是一个白萌新, 以下是我的`rust`之旅, 我只想走得顺一点, 按顺序来

Rust 是一个系统编程语言，它注重于三个方面：安全，速度和并发性

- [安全](#5-rust-%E5%AE%89%E5%85%A8%E4%B8%8E%E9%80%9F%E5%BA%A6), 意味着, 你需要遵循它的规则 > 所有权; 引用和借用; 生命周期
- 速度 [块范围](http://llever.com/gentle-intro/2-structs-enums-lifetimes.zh.html#a%E5%8F%98%E9%87%8F%E7%9A%84%E8%8C%83%E5%9B%B4)
- 并发 待续

### 阅读方式

#### 👀 == 快速看,不需要懂 | 🔍 == 仔细看

---

## 生活

[help me live , live need money 💰](https://github.com/chinanf-boy/live-need-money)


---

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


  - [1. 猜猜看游戏-示例👀](#1-%E7%8C%9C%E7%8C%9C%E7%9C%8B%E6%B8%B8%E6%88%8F-%E7%A4%BA%E4%BE%8B)
  - [2. 第一次使用库-fs_extra👀](#2-%E7%AC%AC%E4%B8%80%E6%AC%A1%E4%BD%BF%E7%94%A8%E5%BA%93-fs_extra)
  - [3. rust-愉快的基础🔍](#3-rust-%E6%84%89%E5%BF%AB%E7%9A%84%E5%9F%BA%E7%A1%80)
  - [4. 尝试项目👀](#4-%E5%B0%9D%E8%AF%95%E9%A1%B9%E7%9B%AE)
  - [5. rust 安全与速度🔍](#5-rust-%E5%AE%89%E5%85%A8%E4%B8%8E%E9%80%9F%E5%BA%A6)
    - [安全](#%E5%AE%89%E5%85%A8)
    - [速度](#%E9%80%9F%E5%BA%A6)
  - [6. 模块/库/Cargo的使用](#6-%E6%A8%A1%E5%9D%97%E5%BA%93cargo%E7%9A%84%E4%BD%BF%E7%94%A8)
    - [快速看版本](#%E5%BF%AB%E9%80%9F%E7%9C%8B%E7%89%88%E6%9C%AC)
    - [放大镜版本](#%E6%94%BE%E5%A4%A7%E9%95%9C%E7%89%88%E6%9C%AC)
  - [7. trait](#7-trait)
  - [8. 并发](#8-%E5%B9%B6%E5%8F%91)
  - [9. explain](#9-explain)
- [有用的链接](#%E6%9C%89%E7%94%A8%E7%9A%84%E9%93%BE%E6%8E%A5)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

---

## 1. 猜猜看游戏-示例👀

> 主要是尝试 

https://github.com/chinanf-boy/guessing_game

## 2. 第一次使用库-fs_extra👀

> 主要是尝试 

https://github.com/chinanf-boy/fs_extra_try

## 3. rust-愉快的基础🔍

经过上面, 快速看, 不需要懂 大致了解了一下, rust

那么我们来下一步看看基础, 只看第一章

- https://slashtutorial.com/rust/1-basics/ `en` 
- http://llever.com/gentle-intro/1-basics.zh.html `zh`

> [ gentle-intro 中文 🇨🇳 翻译 ](https://github.com/chinanf-boy/gentle-intro)

## 4. 尝试项目👀

永远都有前人种树

- [alacritty: 跨平台，GPU加速的终端仿真器](https://github.com/jwilm/alacritty)
- [fd: 一个简单，快速和用户友好的替代方案'find'](https://github.com/sharkdp/fd)
- [xi-editor: 现代编辑器，后端,用Rust编写。](https://github.com/google/xi-editor)
- [xi-mac: xi-editor-官方编辑器的前端。](https://github.com/google/xi-mac)

## 5. rust 安全与速度🔍

然后我们进入, rust 为什么安全和速度的问题

### 安全

- [作用域规则:所有权（ownership）、借用（borrowing）和生命周期（lifetime)](https://rustwiki.org/zh-CN//rust-by-example/scope.html)
- [生命周期与引用有效性](https://kaisery.github.io/trpl-zh-cn/ch10-03-lifetime-syntax.html) 

### 速度

- [块范围](http://llever.com/gentle-intro/2-structs-enums-lifetimes.zh.html#a%E5%8F%98%E9%87%8F%E7%9A%84%E8%8C%83%E5%9B%B4)

> 在这节过后, 你就会发现, rust大部分的编译错误都是为了遵守这套规则

## 6. 模块/库/Cargo的使用

> 到了这里我们应该知道 大多数语言 公认的美好 模块/库/库管理

如果你拥有, 其他语言库的使用情况, 那么你会喜欢, 

### 快速看版本

- `模块` https://rustwiki.org/zh-CN//rust-by-example/mod.html 👀
- `库` https://rustwiki.org/zh-CN//rust-by-example/crates.html 👀
- `Cargo` https://kaisery.github.io/trpl-zh-cn/ch01-03-hello-cargo.html 👀

### 放大镜版本

> 非常不建议, rust 作为 第一语言来说, 这总是意味着要付出更多

- `模块与Cargo` http://chinanf-boy.github.io/gentle-intro/4-modules.zh.html 🔍

## 7. trait

- [trait : 定义共享的行为](https://kaisery.github.io/trpl-zh-cn/ch10-02-traits.html)🔍

> 这部分的, 更应该是说 Rust 的编写代码特点和如何简化代码

## 8. 并发

> 在这里我们来到了, rust 的并发问题 

- [线程,网络和共享](http://llever.com/gentle-intro/7-shared-and-networking.zh.html)👀
- [无畏并发](https://kaisery.github.io/trpl-zh-cn/ch16-00-concurrency.html)🔍

## 9. explain

- [rust-playground](https://github.com/chinanf-boy/rust-playground-explain)

# 有用的链接

- https://play.rust-lang.org/ {官方网上游乐场}
- https://rust.cc/ Rust 中文社区论坛 「较为简单」
- https://github.com/rust-unofficial/awesome-rust {rust 酷库}
- https://rustwiki.org/zh-CN//rust-by-example/index.html {rust-例子「rust by example」中文翻译}
- https://kaisery.github.io/trpl-zh-cn/foreword.html {官方rust第二版-中文翻译}
- https://github.com/chinanf-boy/gentle-intro {温柔的介绍 rust 中文翻译}