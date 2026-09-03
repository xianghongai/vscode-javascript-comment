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

[中文文档](./README.zh-CN.md)

Documentation comments triggered by `@`, so the tag names are one keystroke away instead of something to memorize.

![JavaScript Comment Snippet](https://user-images.githubusercontent.com/58411528/82288531-41d84e00-99d5-11ea-829c-cd6a70b2cc0e.gif)

## Prefixes

1. **Type variants extend the tag with a dot.** `@param.string`, `@property.array`, `@type.generic`. Type `@param.` and the completion list lays out every shape.
2. **Synonyms trigger the primary form.** JSDoc documents `@return`, `@desc`, `@emits`, `@virtual`, `@arg` as alternative spellings. Typing any of them finds the snippet; what gets inserted is the primary tag — `@returns`, `@description`, `@fires`, `@abstract`, `@param`.
3. **`///` opens an empty block comment**, in either dialect.

### Common

Tags that apply to any symbol.

| Prefix         | Alias   | Inserts                                      |
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

### Functions

The `@param` family covers the shapes you hit daily; the per-type variants save typing the brace.

| Prefix               | Alias               | Inserts                                           |
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

### Types

`@type` takes a type expression only — the name comes from the declaration it sits above.

| Prefix              | Alias | Inserts                       |
| ------------------- | ----- | ----------------------------- |
| `@type`             |       | `@type {TYPE}`                |
| `@type.any`         |       | `@type {*}`                   |
| `@type.object`      |       | `@type {Object}`              |
| `@type.string`      |       | `@type {string}`              |
| `@type.number`      |       | `@type {number}`              |
| `@type.boolean`     |       | `@type {boolean}`             |
| `@type.function`    |       | `@type {Function}`            |
| `@type.HTMLElement` |       | `@type {HTMLElement}`         |
| `@type.Node`        |       | `@type {Node}`                |
| `@type.NodeList`    |       | `@type {NodeList}`            |
| `@type.RegExp`      |       | `@type {RegExp}`              |
| `@type.array`       |       | `@type {Object[]}`            |
| `@type.generic`     |       | `@type {Map<string, number>}` |
| `@typedef`          |       | `@typedef {TYPE} Name`        |
| `@typedef.object`   |       | `/**` …                       |
| `@template`         |       | `@template T`                 |
| `@callback`         |       | `/**` …                       |

### Object members

`@property` describes the members of an object or a `@typedef`.

| Prefix                  | Alias   | Inserts                                              |
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

### Classes

| Prefix        | Alias          | Inserts                   |
| ------------- | -------------- | ------------------------- |
| `@class`      | `@constructor` | `/**` …                   |
| `@extends`    | `@augments`    | `@extends {SuperClass}`   |
| `@implements` |                | `@implements {Interface}` |
| `@interface`  |                | `/**` …                   |
| `@abstract`   | `@virtual`     | `@abstract`               |
| `@override`   |                | `@override`               |
| `@readonly`   |                | `@readonly`               |
| `@static`     |                | `@static`                 |

### Modules and events

| Prefix      | Alias                        | Inserts                     |
| ----------- | ---------------------------- | --------------------------- |
| `@module`   |                              | `/** @module moduleName */` |
| `@external` | `@host`                      | `/**` …                     |
| `@fires`    | `@emits`                     | `@fires EventName`          |
| `@listens`  |                              | `@listens EventName`        |
| `@file`     | `@fileoverview`, `@overview` | `/**` …                     |

### TSDoc

These appear in `.ts` and `.tsx` only. TSDoc carries no type annotations — types come from the signature — and the set below is the complete list of standard tags.

| Prefix                  | Alias               | Inserts                            |
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

## References

- [JSDoc](https://jsdoc.app/) · [GitHub](https://github.com/jsdoc/jsdoc)
- [TSDoc](https://tsdoc.org/) · [GitHub](https://github.com/microsoft/tsdoc)
- [TypeScript: JSDoc reference](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html) — which JSDoc tags TypeScript understands in `checkJs`
- [VS Code snippet syntax](https://code.visualstudio.com/docs/editing/userdefinedsnippets)

MIT licensed. See LICENSE.
