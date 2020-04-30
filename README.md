# JavaScript Comment Snippet (Visual Studio Code)

Add ESDoc/JSDoc general comments in TypeScript and JavaScript files.

![JavaScript Comment Snippet](https://raw.githubusercontent.com/caringrun/assets/master/vscode-javascript-comment.gif)

- `@param`
- `@type`
- `@abstract`
- `@access`
- `@class`
- `@constructor`
- `@deprecated`
- `@emits`
- `@example`
- `@experimental`
- `@extends`
- `@external`
- `@ignore`
- `@implements`
- `@interface`
- `@listens`
- `@override`
- `@return`
- `@throws`
- `@typedef`
- `@return`
- `@note`

## Type Syntax

| type               | syntax                                                                     |
|--------------------|----------------------------------------------------------------------------|
| Simple             | `@param {string} param - description`                                      |
| Array              | `@param {string[]} param - description`                                    |
| Nullable           | `@param {?Object} param - description`                                     |
| Not Nullable       | `@param {!Object} param - description`                                     |
| Union              | `@param {number|string} param - description`                               |
| Nullable and Union | `@param {?(number|string)} param - description`                            |
| Spread             | `@param {...number} param - description`                                   |
| Optional           | `@param {number} [param] - description`                                    |
| Default            | `@param {number} [param=10] - description`                                 |
| Function           | `@param {function(foo: number, bar: string): boolean} param - description` |
| Generics           | `@param {Map<number, string>} param - description`                         |
| Record             | `@param {{foo: ?number, bar: string}} param - description`                 |

## Snippets

### For Member And Variable

`doc.type` or `@type`

```javascript
/** @type {type} - description*/
```

`doc.type.object` or `@type.object`

```javascript
/**
 * @type {Object} obj
 * @property {type} obj.property - description
 */
```

### For Method And Function

`doc.reutrn` or `@reutrn`

```javascript
@return {type} - description
```

`doc.requires` or `@requires`

```javascript
@requires {module} - description
```

`doc.param` or `@param`

```javascript
/**
 * @param {type} property - description.
 */
```

`doc.param.inner` or `@param.inner`

```javascript
@param {type} property - description.
```

`doc.param.object` or `@param.object`

```javascript
/**
 * @param {Object} param - description.
 * @param {type} param.property - property description.
 */
```

`doc.param.object.inner` or `@param.object.inner`

```javascript
@param {Object} param - description.
* @param {type} param.property - property description.
```

`doc.abstract` or `@abstract`

```javascript
/**
 * this method must be overridden by sub class.
 * @abstract
 */
```

`doc.override` or `@override`

```javascript
/**
 * @override
 */
```

`doc.emits` or `@emits`

```javascript
/**
 * @emits {MyEvent} emit event when ...
 */
```

`doc.listens` or `@listens`

```javascript
/**
 * @listens {MyEvent} listen event because ...
 */
```

`doc.throws` or `@throws`

```javascript
/**
 * @throws {MyError} throw error when ...
 */
```

### For Class

`doc.class ` or `@class `

```javascript
/**
 * @class
 * description.
 */
```

`doc.extends` or `@extends`

```javascript
/**
 * @extends {SuperClass}
 */
```

`doc.interface` or `@interface`

```javascript
/**
 * @interface
 */
```

`doc.implements` or `@implements`

```javascript
/**
 * @implements {MyInterface}
 */
```

`doc.constructor` or `@constructor`

```javascript
/** @constructor */
```

### For Common

`bc` or `///`, **B**lock **C**omments

```javascript
/**
 *
 */
```

`doc.access` or `@access`

```javascript
/**
 * @access public|protected|package|private
 */
```

`doc.deprecated` or `@deprecated`

```javascript
/**
 * @deprecated description
 */
```

`doc.experimental` or `@experimental`

```javascript
/**
 * @experimental description
 */
```

`doc.example` or `@example`

```javascript
/**
 * @example
 *
 */
```

`doc.ignore` or `@ignore`

```javascript
/**
 * @ignore
 */
```

`doc.license` or `@license`

```javascript
/**
 * @license
 * Copyright NAME. All Rights Reserved.
 *
 * Use of this source code is governed by an MIT-style license that can be
 * found in the LICENSE file in the root directory of this source tree.
 */
```

### For Virtual

`doc.external` or `@external`

```javascript
/**
 * @external {identifier} URL
 */
```

`doc.typedef` or `@typedef`

```javascript
/**
 * @typedef {type} type
 */
```

`doc.typedef.object` or `@typedef.object`

```javascript
/**
 * @typedef {Object} name
 * @property {type} description.
 */
```

## Resources

- [jsdoc - Github](https://github.com/jsdoc/jsdoc)
- [esdoc - Github](https://github.com/esdoc/esdoc)

## License

MIT License
