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
- `@throws`
- `@typedef`

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

## For Member And Variable

`doc.type`

```javascript
/** @type {type} - description*/
```

`doc.type.object`

```javascript
/**
 * @type {Object} obj
 * @property {type} obj.property - description
 */
```


## For Method And Function

`doc.param`

```javascript
/**
 * @param {type} property - description.
 */
```

`param`, or `doc.param.single`

```javascript
@param {type} property - description.
```

`doc.param.object`

```javascript
/**
 * @param {Object} param - description.
 * @param {type} param.property - property description.
 */
```

`param.object`, or `doc.param.object.single`

```javascript
@param {Object} param - description.
* @param {type} param.property - property description.
```


`doc.abstract`

```javascript
/**
 * this method must be overridden by sub class.
 * @abstract
 */
```

`doc.override`

```javascript
/**
 * @override
 */
```

`doc.emits`

```javascript
/**
 * @emits {MyEvent} emit event when ...
 */
```

`doc.listens`

```javascript
/**
 * @listens {MyEvent} listen event because ...
 */
```

`doc.throws`

```javascript
/**
 * @throws {MyError} throw error when ...
 */
```

## For Class

`doc.class `

```javascript
/**
 * @class
 * description.
 */
```

`doc.extends`

```javascript
/**
 * @extends {SuperClass}
 */
```

`doc.interface`

```javascript
/**
 * @interface
 */
```

`doc.implements`

```javascript
/**
 * @implements {MyInterface}
 */
```

`doc.constructor`

```javascript
/** @constructor */
```

## For Common

`bc` or `///`, **B**lock **C**omments

```javascript
/**
 *
 */
```

`doc.access`

```javascript
/**
 * @access public|protected|package|private
 */
```

`doc.deprecated`

```javascript
/**
 * @deprecated description
 */
```

`doc.experimental`

```javascript
/**
 * @experimental description
 */
```

`doc.example`

```javascript
/**
 * @example
 *
 */
```

`doc.ignore`

```javascript
/**
 * @ignore
 */
```


## For Virtual

`doc.external`

```javascript
/**
 * @external {identifier} URL
 */
```

`doc.typedef`

```javascript
/**
 * @typedef {type} type
 */
```

`doc.typedef.object`

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
