# JavaScript Comment Snippet (Visual Studio Code)

<p align="center">
  <a href="https://github.com/xianghongai/vscode-javascript-comment">
    <img src="https://img.shields.io/github/repo-size/xianghongai/vscode-javascript-comment?style=plastic&color=4ac51c" alt="Repo Size">
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=nicholashsiang.vscode-javascript-comment">
    <img src="https://vsmarketplacebadges.dev/version/nicholashsiang.vscode-javascript-comment.svg?style=plastic&color=ffbf40" alt="Visual Studio Marketplace Version">
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=nicholashsiang.vscode-javascript-comment">
    <img src="https://vsmarketplacebadges.dev/downloads-short/nicholashsiang.vscode-javascript-comment.svg?style=plastic&color=4ac51c" alt="Downloads">
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=nicholashsiang.vscode-javascript-comment">
    <img src="https://vsmarketplacebadges.dev/rating-short/nicholashsiang.vscode-javascript-comment.svg?style=plastic&color=4ac51c" alt="Rating">
  </a>
  <a href="https://github.com/xianghongai/vscode-javascript-comment/blob/HEAD/LICENSE">
    <img src="https://img.shields.io/github/license/xianghongai/vscode-javascript-comment?style=plastic&color=4ac51c" alt="License">
  </a>
</p>

[English](./README.md)

用 `@` 触发文档注释，标签名随手可得，不必去记。

![JavaScript Comment Snippet](https://user-images.githubusercontent.com/58411528/82288531-41d84e00-99d5-11ea-829c-cd6a70b2cc0e.gif)

## 前缀清单

1. **类型变体以点号延伸。** `@param.string`、`@property.array`、`@type.generic`。打出 `@param.` 就能在补全列表里摊开全部形态。
2. **同义写法触发规范形式。** JSDoc 把 `@return`、`@desc`、`@emits`、`@virtual`、`@arg` 列为另一种拼法。输入其中任意一个都能找到片段，插入的则是主标签：`@returns`、`@description`、`@fires`、`@abstract`、`@param`。
3. **`///` 起一个空注释块**，两种规范下都可用。

### 通用

适用于任何符号的标签。

| 前缀           | 别名    | 插入内容                                     |
| -------------- | ------- | -------------------------------------------- |
| `///`          |         | `/**` …                                      |
| `@description` | `@desc` | `@description description`                   |
| `@example`     |         | `@example` …                                 |
| `@deprecated`  |         | `@deprecated since version X, use Y instead` |
| `@see`         |         | `@see {@link OtherSymbol}}`                  |
| `@link`        |         | `{@link namepath\|link text}`                |
| `@since`       |         | `@since 1.0.0`                               |
| `@version`     |         | `@version 1.0.0`                             |
| `@todo`        |         | `@todo description`                          |
| `@ignore`      |         | `@ignore`                                    |
| `@access`      |         | `@access public`                             |
| `@license`     |         | `/**` …                                      |

### 函数

`@param` 族覆盖日常会遇到的各种形态，按类型细分的变体可以省去手写花括号。

| 前缀                 | 别名                | 插入内容                                          |
| -------------------- | ------------------- | ------------------------------------------------- |
| `@param`             | `@arg`, `@argument` | `@param {TYPE} name - description`                |
| `@param.optional`    |                     | `@param {TYPE} [name] - description`              |
| `@param.default`     |                     | `@param {TYPE} [name=defaultValue] - description` |
| `@param.array`       |                     | `@param {Object[]} name - description`            |
| `@param.generic`     |                     | `@param {Map<string, number>} name - description` |
| `@param.any`         |                     | `@param {*} name - description`                   |
| `@param.object`      |                     | `@param {Object} name - description`              |
| `@param.string`      |                     | `@param {string} name - description`              |
| `@param.number`      |                     | `@param {number} name - description`              |
| `@param.boolean`     |                     | `@param {boolean} name - description`             |
| `@param.function`    |                     | `@param {Function} name - description`            |
| `@param.HTMLElement` |                     | `@param {HTMLElement} name - description`         |
| `@param.Node`        |                     | `@param {Node} name - description`                |
| `@param.NodeList`    |                     | `@param {NodeList} name - description`            |
| `@param.RegExp`      |                     | `@param {RegExp} name - description`              |
| `@returns`           | `@return`           | `@returns {TYPE} description`                     |
| `@returns.promise`   |                     | `@returns {Promise<TYPE>} description`            |
| `@throws`            | `@exception`        | `@throws {Error} description`                     |
| `@yields`            | `@yield`            | `@yields {TYPE} description`                      |
| `@async`             |                     | `@async`                                          |
| `@this`              |                     | `@this {TYPE}`                                    |
| `@requires`          |                     | `@requires moduleName`                            |

### 类型

`@type` 只接受类型表达式，名字来自它所修饰的那条声明。

| 前缀                | 别名 | 插入内容                      |
| ------------------- | ---- | ----------------------------- |
| `@type`             |      | `@type {TYPE}`                |
| `@type.any`         |      | `@type {*}`                   |
| `@type.object`      |      | `@type {Object}`              |
| `@type.string`      |      | `@type {string}`              |
| `@type.number`      |      | `@type {number}`              |
| `@type.boolean`     |      | `@type {boolean}`             |
| `@type.function`    |      | `@type {Function}`            |
| `@type.HTMLElement` |      | `@type {HTMLElement}`         |
| `@type.Node`        |      | `@type {Node}`                |
| `@type.NodeList`    |      | `@type {NodeList}`            |
| `@type.RegExp`      |      | `@type {RegExp}`              |
| `@type.array`       |      | `@type {Object[]}`            |
| `@type.generic`     |      | `@type {Map<string, number>}` |
| `@typedef`          |      | `@typedef {TYPE} Name`        |
| `@typedef.object`   |      | `/**` …                       |
| `@template`         |      | `@template T`                 |
| `@callback`         |      | `/**` …                       |

### 对象成员

`@property` 用于描述对象或 `@typedef` 的成员。

| 前缀                    | 别名    | 插入内容                                             |
| ----------------------- | ------- | ---------------------------------------------------- |
| `@property`             | `@prop` | `@property {TYPE} name - description`                |
| `@property.optional`    |         | `@property {TYPE} [name] - description`              |
| `@property.array`       |         | `@property {Object[]} name - description`            |
| `@property.generic`     |         | `@property {Map<string, number>} name - description` |
| `@property.any`         |         | `@property {*} name - description`                   |
| `@property.object`      |         | `@property {Object} name - description`              |
| `@property.string`      |         | `@property {string} name - description`              |
| `@property.number`      |         | `@property {number} name - description`              |
| `@property.boolean`     |         | `@property {boolean} name - description`             |
| `@property.function`    |         | `@property {Function} name - description`            |
| `@property.HTMLElement` |         | `@property {HTMLElement} name - description`         |
| `@property.Node`        |         | `@property {Node} name - description`                |
| `@property.NodeList`    |         | `@property {NodeList} name - description`            |
| `@property.RegExp`      |         | `@property {RegExp} name - description`              |

### 类

| 前缀          | 别名           | 插入内容                  |
| ------------- | -------------- | ------------------------- |
| `@class`      | `@constructor` | `/**` …                   |
| `@extends`    | `@augments`    | `@extends {SuperClass}`   |
| `@implements` |                | `@implements {Interface}` |
| `@interface`  |                | `/**` …                   |
| `@abstract`   | `@virtual`     | `@abstract`               |
| `@override`   |                | `@override`               |
| `@readonly`   |                | `@readonly`               |
| `@static`     |                | `@static`                 |

### 模块与事件

| 前缀        | 别名                         | 插入内容                    |
| ----------- | ---------------------------- | --------------------------- |
| `@module`   |                              | `/** @module moduleName */` |
| `@external` | `@host`                      | `/**` …                     |
| `@fires`    | `@emits`                     | `@fires EventName`          |
| `@listens`  |                              | `@listens EventName`        |
| `@file`     | `@fileoverview`, `@overview` | `/**` …                     |

### TSDoc

这些只在 `.ts` 与 `.tsx` 中出现。TSDoc 不带类型标注（类型由签名提供），下表即其标准标签的完整集合。

| 前缀                    | 别名                | 插入内容                           |
| ----------------------- | ------------------- | ---------------------------------- |
| `///`                   |                     | `/**` …                            |
| `@param`                | `@arg`, `@argument` | `@param name - description`        |
| `@returns`              | `@return`           | `@returns description`             |
| `@typeParam`            |                     | `@typeParam T - description`       |
| `@throws`               |                     | `@throws description`              |
| `@remarks`              |                     | `@remarks` …                       |
| `@example`              |                     | `@example` …                       |
| `@defaultValue`         |                     | `@defaultValue value`              |
| `@deprecated`           |                     | `@deprecated use Y instead`        |
| `@see`                  |                     | `@see {@link OtherSymbol}}`        |
| `@link`                 |                     | `{@link Symbol\|link text}`        |
| `@label`                |                     | `@label LABEL_NAME`                |
| `@inheritDoc`           |                     | `@inheritDoc {@link OtherSymbol}}` |
| `@privateRemarks`       |                     | `@privateRemarks` …                |
| `@packageDocumentation` |                     | `/**` …                            |
| `@decorator`            |                     | `@decorator `@decoratorName()``    |
| `@alpha`                |                     | `@alpha`                           |
| `@beta`                 |                     | `@beta`                            |
| `@public`               |                     | `@public`                          |
| `@internal`             |                     | `@internal`                        |
| `@experimental`         |                     | `@experimental`                    |
| `@eventProperty`        |                     | `@eventProperty`                   |
| `@override`             |                     | `@override`                        |
| `@sealed`               |                     | `@sealed`                          |
| `@virtual`              |                     | `@virtual`                         |
| `@readonly`             |                     | `@readonly`                        |

## 官方依据

- [JSDoc](https://jsdoc.app/) · [GitHub](https://github.com/jsdoc/jsdoc)
- [TSDoc](https://tsdoc.org/) · [GitHub](https://github.com/microsoft/tsdoc)
- [TypeScript：JSDoc 支持范围](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html)：`checkJs` 下 TypeScript 认得哪些 JSDoc 标签
- [VS Code 片段语法](https://code.visualstudio.com/docs/editing/userdefinedsnippets)

基于 MIT 协议开源，详见 LICENSE。
