<p>
  <h1 align="center">JavaScript Comment Snippet (Visual Studio Code)</h1>
</p>

<p align="center">
  <a href="https://github.com/xianghongai/vscode-javascript-comment">
    <img src="https://img.shields.io/github/repo-size/xianghongai/vscode-javascript-comment?style=plastic&color=4ac51c">
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=nicholashsiang.vscode-javascript-comment">
    <img src="https://vsmarketplacebadge.apphb.com/version-short/nicholashsiang.vscode-javascript-comment.svg?style=plastic&color=ffbf40">
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=nicholashsiang.vscode-javascript-comment">
    <img src="https://vsmarketplacebadge.apphb.com/installs-short/nicholashsiang.vscode-javascript-comment.svg?style=plastic&color=4ac51c">
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=nicholashsiang.vscode-javascript-comment">
    <img src="https://vsmarketplacebadge.apphb.com/rating-short/nicholashsiang.vscode-javascript-comment.svg?style=plastic&color=4ac51c">
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=nicholashsiang.vscode-javascript-comment">
    <img src="https://img.shields.io/github/license/xianghongai/vscode-javascript-comment?maxAge=2592000&style=plastic&color=4ac51c">
  </a>
</p>

[中文](./README_CN.md).

Add ESDoc/JSDoc general comments in TypeScript and JavaScript files. 

Generate comments statically, not responsive. For parameter functions or variables of existing types, it is recommended to use the built-in `/**` to trigger.

![JavaScript Comment Snippet](https://user-images.githubusercontent.com/58411528/82288531-41d84e00-99d5-11ea-829c-cd6a70b2cc0e.gif)

## Settings

If that doesn't work, you may need to configure the editor.

`Ctrl + Shift + P` / `⇧ + ⌘ + P` → `Preferences: Open Settings (JSON)`

```json
  "editor.quickSuggestions": {
    "other": true,
    "comments": true,
    "strings": false
  },
```

## Snippets

- Comment Blocks
- Common
- Type Syntax
- Function
- Class
- Misc

Instructions with `single`, without triggering `///`, will generate a complete comment fragment.

### Comment Blocks

Generate a comment fragment triggered by `///`:

`///` →

```js
/**
 * description
 */
```

Then use the following categories to add specific annotation content.

### Common

- `@access`
- `@deprecated`
- `@desc`
- `@example`
- `@experimental`
- `@ignore`
- `@link`
- `@see`
- `@note`
- `@since` → `@since MAJOR.MINOR.PATCH`
- `@todo`
- `@version` → `@version MAJOR.MINOR.PATCH`
- `@license`

### Type Syntax

| prefix              | body                                      |
|---------------------|-------------------------------------------|
| `@param`            | `@param {TYPE} param - description`    |
| `@param.property`   | `@param {?TYPE} param.name - description` |
| `@param.boolean`    | `@param {boolean} param - description`    |
| `@param.Object`     | `@param {Object} param - description`     |
| `@param.string`     | `@param {string} param - description`     |
| `@param.number`     | `@param {number} param - description`     |
| `@param.boolean`    | `@param {boolean} param - description`    |
| `@param.Function`   | `@param {Function} param - description`   |
| `@param.DOMElement` | `@param {DOMElement} param - description` |
| `@param.Node`       | `@param {Node} param - description`       |
| `@param.NodeList`   | `@param {NodeList} param - description`   |
| `@param.RegExp`     | `@param {RegExp} param - description`     |
| `@type`             | `@type {TYPE} - description`              |
| `@type.property`    | `@property {TYPE} name - description`     |
| `@typedef`          | `@typedef {TYPE} name - description`      |
| `@typedef.property` | `@property {TYPE} name - description`     |

### Function

- `@return (single)`
- `@return`
- `@return property`
- `@requires`
- `@abstract`
- `@emits`
- `@listens`
- `@override`
- `@throws`

### Class

- `@class`
- `@class.extends`, `@extends`
- `@class.interface`, `@interface`
- `@class.implements`, `@implements`
- `@class.constructor`, `@constructor`
- `@namespace`

### Misc

- `@external`
- `@module`

## Resources

- [jsdoc - Github](https://github.com/jsdoc/jsdoc)
- [esdoc - Github](https://github.com/esdoc/esdoc)


## `@param` Syntax

| type               | syntax                                                                     |
|--------------------|----------------------------------------------------------------------------|
| Simple             | `@param {string} param - description`                                      |
| Array              | `@param {string[]} param - description`                                    |
| Nullable           | `@param {?Object} param - description`                                     |
| Not Nullable       | `@param {!Object} param - description`                                     |
| Union              | `@param {number\|string} param - description`                               |
| Nullable and Union | `@param {?(number\|string)} param - description`                            |
| Spread             | `@param {...number} param - description`                                   |
| Optional           | `@param {number} [param] - description`                                    |
| Default            | `@param {number} [param=10] - description`                                 |
| Function           | `@param {function(foo: number, bar: string): boolean} param - description` |
| Generics           | `@param {Map<number, string>} param - description`                         |
| Record             | `@param {{foo: ?number, bar: string}} param - description`                 |

## License

MIT License
