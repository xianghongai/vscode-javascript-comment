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

Quickly generate JavaScript/TypeScript comments according to JSDoc, ESDoc and TSDoc rules, and use `@` to trigger to reduce the burden of memory.

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

### Type Syntax

#### For Param

| prefix                                  | body                                                 |
|-----------------------------------------|------------------------------------------------------|
| `@param` →                              | `@param {TYPE} param - description`                  |
| `@param.property` →                     | `@param {?TYPE} param.name - description`            |
| `@param.any` / `@paa →                  | `@param {\*} param - description`                    |
| `@param.object` / `@pao` / `@ppo` →     | `@param {Object} param - description`                |
| `@param.array` / `@paar` / `@ppar` →    | `@param {Object[]} param - description`              |
| `@param.string` / `@pas` / `@pps` →     | `@param {string} param - description`                |
| `@param.number` / `@panu` / `@ppn` →    | `@param {number} param - description`                |
| `@param.boolean` / `@pab` / `@ppb` →    | `@param {boolean} param - description`               |
| `@param.Function` / `@paf` / `@ppf` →   | `@param {Function} param - description`              |
| `@param.DOMElement` / `@pad` / `@ppd` → | `@param {DOMElement} param - description`            |
| `@param.Node` / `@pan` / `@ppnode` →    | `@param {Node} param - description`                  |
| `@param.NodeList` / `@panl` / `@ppnl` → | `@param {NodeList} param - description`              |
| `@param.RegExp` / `@pare` / `@ppre` →   | `@param {RegExp} param - description`                |
| `@param.generics` / `@pag` / `@ppg` →   | `@param {GenericIdentity<Type>} param - description` |

#### For Member And Variable

| prefix               | body                                               |
|----------------------|----------------------------------------------------|
| `@typeParam` →       | `@typeParam {TYPE} Name - description`, (* TS Doc) |
| `@type` →            | `@type {TYPE} - description`                       |
| `@type.boolean` →    | `@type {boolean} type - description`               |
| `@type.Object` →     | `@type {Object} type - description`                |
| `@type.string` →     | `@type {string} type - description`                |
| `@type.number` →     | `@type {number} type - description`                |
| `@type.boolean` →    | `@type {boolean} type - description`               |
| `@type.Function` →   | `@type {Function} type - description`              |
| `@type.DOMElement` → | `@type {DOMElement} type - description`            |
| `@type.Node` →       | `@type {Node} type - description`                  |
| `@type.NodeList` →   | `@type {NodeList} type - description`              |
| `@type.RegExp` →     | `@type {RegExp} type - description`                |

| prefix                   | body                                            |
|--------------------------|-------------------------------------------------|
| `@property` →            | `@property {TYPE} property - description`       |
| `@property.boolean` →    | `@property {boolean} property - description`    |
| `@property.Object` →     | `@property {Object} property - description`     |
| `@property.string` →     | `@property {string} property - description`     |
| `@property.number` →     | `@property {number} property - description`     |
| `@property.boolean` →    | `@property {boolean} property - description`    |
| `@property.Function` →   | `@property {Function} property - description`   |
| `@property.DOMElement` → | `@property {DOMElement} property - description` |
| `@property.Node` →       | `@property {Node} property - description`       |
| `@property.NodeList` →   | `@property {NodeList} property - description`   |
| `@property.RegExp` →     | `@property {RegExp} property - description`     |

Example:

```js
class MyClass {
  constructor() {
    /**
     * @type {number}
     */
    this.foo = 123;

    /**
     * @type {Object}
     * @property {number} p.foo
     * @property {string} p.bar
     */
    this.bar = { foo: 123, bar: 'abc' };
  }

  /** @type {string} */
  get baz() {}

  /** @type {string} */
  set baz(v) {}

  /**
   * @param {number} param - this is p description.
   * @return {Object} this is description.
   * @property {number} foo this is description.
   * @property {number} bar this is description.
   */
  qux(param) {}
}
```

#### For Virtual Type

| prefix       | body                                 |
|--------------|--------------------------------------|
| `@typedef` → | `@typedef {TYPE} Name - description` |

Example:

```js
/**
 * A number, or a string containing a number.
 * @typedef {(number|string)} NumberLike
 */

/**
 * Set the magic number.
 * @param {NumberLike} x - The magic number.
 */
function setMagicNumber(x) { }
```

### Function

| prefix                    | body                                                                                        |
|---------------------------|---------------------------------------------------------------------------------------------|
| `@return`/`@rt` →         | `@return {TYPE} description`                                                                |
| `@return.promise`/`@rp` → | `@return {Promise<TYPE>} description`                                                       |
| `@return (single)` →      | `/** @return {TYPE} description */`                                                         |
| `@requires` →             | `@requires module`                                                                          |
| `@emits` →                | `/** @emits {eventName} emit event when ... */`                                             |
| `@listens` →              | `/** @listens {eventName} listen event because ... */`                                      |
| `@throws` →               | `/** @throws {errorType} Will throw an error if argument is null./Argument x must be x. */` |

Example:

```js
/**
 * function description
 * @param {Object} param - this is object param.
 * @param {number} param.foo - this is property param.
 * @param {string} param.bar - this is property param.
 */
function myFunc(param) {}

/**
 * function description
 * @param {{foo: number, bar: string}} param - this is object param.
 */
function myFunc(param) {}

/**
 * function description
 * @param {{foo: ?number, bar: string}} param - this is nullable property.
 */
function myFunc(param) {}

/**
 * function description
 * @param {{foo: number, bar: string}} param - this is object destructuring..
 */
function myFunc({ foo, bar }) {}

/**
 * @param {number} [param] - this is optional param.
 * @param {number} [param=10] - this is default param.
 * @param {?number} param - this is nullable param.
 * @param {!Object} param - this is not nullable param.
 * @param {?(number|string)} param - this is nullable and union param.
 * @param {function(foo: number, bar: string): boolean} param - this is function param.
 * @param {Array<string>} param - this is Array param.
 * @param {Map<number, string>} param - this is Map param.
 */
function myFunc(param) {}
```

### Class

| prefix                                                       | body                         |
|--------------------------------------------------------------|------------------------------|
| `@class` →                                                   | `/** @class description. */` |
| `@class.extends`, `@extends` →                               | `@extends {SuperClass}`      |
| `@class.interface`, `@interface` →                           | `/** @interface */`          |
| `@class.implements`, `@implements` →                         | `@implements {Interface}`    |
| `@class.constructor`, `@constructor` →                       | `/** @constructor */`        |
| `@class.virtual`/`@class.abstract`, `@virtual`/`@abstract` → | `/** @virtual */`            |
| `@class.sealed`, `@sealed` →                                 | `/** @sealed */`             |
| `@class.override`, `@override` →                             | `/** @override */`           |

### Common

- `@access`
- `@deprecated`
- `@desc`
- `@example`
- `@experimental`
- `@ignore`
- `@link` → `{@link <identifier>}`
- `@see` → `@see <URL>`
- `@note`
- `@since` → `@since MAJOR.MINOR.PATCH`
- `@todo` → `@todo description`
- `@version` → `@version MAJOR.MINOR.PATCH`
- `@internal`
- `@license`

### Misc

- `@external`
- `@module`

## Resources

- [JSDoc - Github](https://github.com/jsdoc/jsdoc)/[https://jsdoc.app/](https://jsdoc.app/)
- [ESDoc - Github](https://github.com/esdoc/esdoc)/[https://esdoc.org/](https://esdoc.org/)
- [TSDoc - Github](https://github.com/microsoft/tsdoc)/[https://tsdoc.org/](https://tsdoc.org/)

## `@param`/`@property` Syntax

| type               | syntax                                                                     |
|--------------------|----------------------------------------------------------------------------|
| Simple             | `@param {string} param - description`                                      |
| Array              | `@param {string[]} param - description`                                    |
| Nullable           | `@param {?Object} param - description`                                     |
| Not Nullable       | `@param {!Object} param - description`                                     |
| Union              | `@param {number\|string} param - description`                              |
| Nullable and Union | `@param {?(number\|string)} param - description`                           |
| Spread             | `@param {...number} param - description`                                   |
| Optional           | `@param {number} [param] - description`                                    |
| Default            | `@param {number} [param=10] - description`                                 |
| Function           | `@param {function(foo: number, bar: string): boolean} param - description` |
| Generics           | `@param {Map<number, string>} param - description`                         |
| Record             | `@param {{foo: ?number, bar: string}} param - description`                 |

## License

MIT License
