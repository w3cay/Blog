---
layout: "post"
title: " JavaScript 静态类型检查方案"
date: "2017-06-10 20:50"
tags: [JavaScript, Typescipt, Flow]
---

TypeScipt 中的类型检查是 Javascipt 所缺少的，当考虑到项目的可靠性时，这个特性是必不可少的，目前的可实行方案有 TypeScipt 和 Flow 可供选择，下面和 ES6 做下比较和分析

## 方案比较

方案 | 简介  |生态支持 | 学习成本  | 迁移成本 | 使用收益
---- | --- | ---| ---- | --- | ---| --- | ---
ES6 | 是一门弱类型，面向对象（基于原型）的高级编程语言 | 目前部分 ES6 特性在现代浏览器得到支持，通过 Babel 转译为 ES5 可使用大部分特性 | 成本较低 | 目前项目已配置 ES6 编译环境，成本基本为零 | 语法相比之前的版本更加简洁和高效
TypeScript | TypeScript是一种由微软开发的自由和开源的编程语言。它是JavaScript的一个严格超集，并添加了可选的静态类型和基于类的面向对象编程 | TypeScript 是微软的一个开源项目，目前最新版本 2.3，GitHub Star 数达到 22761,工具链上与 Gulp, Webpack 都有很好地支持,全平台  | Typescript 的学习成本比较高，他包含了泛型、接口等很多 java、C# 的概念 | 由于 TypeScript 是一整套的方案，所以老项目迁移困难，新项目则成本较低 | 因为 TS 提供了很多强类型语言的功能，所以可以使得代码更健壮，编译后的代码也是针对 V8 等 js 引擎优化过的，所以执行效率也不会太慢，通过编辑器的支持，可使开发调试更有效率
Flow | 由 FaceBook 开发的一套 JavaScript 类型检查工具 | Flow 是FaceBook 的一个开源项目，目前最新版本 0.47.0 ，GitHub Star 数达到 12122,工具链上与 Gulp, Webpack 都有很好地支持, 全平台 | Flow 的学习成本相比较 TypeScript 较低 | Flow 的可配置性和灵活度较高，可选择单个文件或整个项目的类型检查处理，并且基于和 Babel 搭配使用，所以项目迁移成本较低 | 同 TypeScipt

## 结论 
对于当前项目，从平缓迁移的角度看，Flow 更符合当前的需求。而 Typescript 更适合于新项目或者大型的应用项目，可在团队内部项目试用，进行踩坑沉淀，待整个生态摸索的较为成熟再逐步应用到业务并在团队推广，并同时统一团队编码风格，提高团队协作效率。

<!--ES6 | 是一门弱类型，面向对象（基于原型）的高级编程语言 | LearnShare |- |-|-|s
TypeScript |  TypeScript是一种由微软开发的自由和开源的编程语言。它是JavaScript的一个严格超集，并添加了可选的静态类型和基于类的面向对象编程 | LearnShare |- |-|-|
Flow | 由 FaceBook 开发的一套 JavaScript 类型检查工具 | LearnShare |- |-|-|-->