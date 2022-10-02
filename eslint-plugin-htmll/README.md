# ES Lint
## 特徴
・プロジェクトに合わせて自由にルールのON/OFFができる
・豊富なビルトインルールと充実したプラグインがある
・ECMA Script、JSX記法をサポート
・Babelと連携可能
・自動修正可能

## インストール
```
npm install --save-dev eslint-plugin-html

npm init @eslint/config
? How would you like to use ESLint? …
  To check syntax only
  To check syntax and find problems
❯ To check syntax, find problems, and enforce code style

  構文チェックのみ
  構文チェックと問題の発見
  構文チェックと問題の発見とコードスタイルの矯正

? What type of modules does your project use? …
  JavaScript modules (import/export)
❯ CommonJS (require/exports)
  None of these

? プロジェクトではどのようなモジュールを使用していますか？...
  JavaScript モジュール (インポート/エクスポート)
  CommonJS (require/exports)です。
  該当するものはありません

? Which framework does your project use? …
  React
  Vue.js
❯ None of these

? Does your project use TypeScript? › No / Yes

? Where does your code run? …  (Press <space> to select, <a> to toggle all, <i> to invert selection)
✔ Browser
✔ Node

? Which style guide do you want to follow? (Use arrow keys)
❯ Airbnb: https://github.com/airbnb/javascript
  Standard: https://github.com/standard/standard
  Google: https://github.com/google/eslint-config-google

? Which style guide do you want to follow? …
❯ Standard: https://github.com/standard/eslint-config-standard-with-typescript
  XO: https://github.com/xojs/eslint-config-xo-typescript

? What format do you want your config file to be in? …
  JavaScript
❯ YAML
  JSON

? Which package manager do you want to use? …
❯ npm
  yarn
  pnpm

```

##設定
package.jsonのscriptにエイリアスを設定
```
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "lint": "eslint 対象のjsファイル"
  },
```

.eslintrc.jsonにルールを設定
```
// "off"/"warn"/"error"
{
  "rules": {
    "no-extra-semi": "warn"
  }
}
```
