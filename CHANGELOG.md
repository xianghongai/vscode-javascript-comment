# Changelog

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## 1.2.1 (2026-09-03)

- Publish extension to Open VSX Registry alongside the VS Code Marketplace
- Update CI workflow to build the VSIX package once and reuse it across both marketplaces

## 1.2.0 (2026-09-03)

- Unify packaging and publishing scripts to `vsce:package` and `vsce:publish`
- Update GitHub Actions CI workflow to use `pnpm run vsce:publish`

## 1.1.0 (2026/09/02)

- 片段按语言分流：`.js` / `.jsx` / `.vue` 中提供 JSDoc（类型写在花括号里），`.ts` / `.tsx` 中提供 TSDoc（不写花括号，类型由 TypeScript 签名提供）。同一个前缀在两种文件里各自插入正确的形态
- 新增 `.tsx` 支持，此前完全未覆盖
- 修正产出非法语法的片段：`@type` 不再附带名字与描述（JSDoc 的 `@type` 只接受类型表达式）、`@typeParam` 去掉花括号（TSDoc 无类型标注）、`@typedef` 两个占位符编号冲突导致无法分别填写
- 同义写法改为触发规范形式：输入 `@return` / `@desc` / `@emits` / `@virtual` / `@arg` 仍能命中，插入的是 `@returns` / `@description` / `@fires` / `@abstract` / `@param`
- 类型变体中的 `DOMElement` 换成 `HTMLElement`，前者并非真实存在的类型
- 补齐 TSDoc 标准标签，并新增 `@yields`、`@async`、`@template`、`@callback`、`@file` 等 JSDoc 常用标签
- 移除不产出任何标签的 `@note`
- 用 oxfmt/oxlint 替换了原来的 prettier/eslint

## 1.0.0 (2022/03/27)

- 结合 JSDoc、ESDoc 和 TSDoc，在 VS Code 中以代码片断的方式，快捷生成 JavaScript 注释，采用 `@` 触发，减轻记忆成本。
