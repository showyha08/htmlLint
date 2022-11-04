# html-ESLint
html-ESLintのルールを以下の通り有効化する。

## html-ESLintの設定について
HTMLはThymeleafで書かれているパーツとして利用するファイルが多数存在する。
Thymeleafで書かれたHTMLがエラーで大量に検知されないように有効化するルールを選定した。

## html-ESLintのルール一覧
[元ネタ](https://github.com/yeonjuan/html-eslint/blob/main/docs/all-rules.md)

### Best Practice
| rule | description | 日本語訳 |
| :--- | :---| :--- |
| [@html-eslint/no-duplicate-id](rules/no-duplicate-id) | Disallow to use duplicate id | idの重複禁止 |
| [@html-eslint/no-inline-styles](rules/no-inline-styles) | Disallow using inline style | インラインstyleを禁止 |
| [@html-eslint/require-li-container](rules/require-li-container) | Enforce `<li>` to be in  `<ul>`, `<ol>` or `<menu>`. | li,ulはol,menu内の利用に強制 |
| [@html-eslint/no-obsolete-tags](rules/no-obsolete-tags) | Disallow to use obsolete elements in HTML5 | 廃止タグの利用禁止 |
| [@html-eslint/require-closing-tags](rules/require-closing-tags) | Require closing tags. | 閉じタグ必須 |
| [@html-eslint/no-target-blank](rules/no-target-blank) | Disallow usage of unsafe `target='_blank'` | _blankの禁止 |
| [@html-eslint/no-duplicate-attrs](rules/no-duplicate-attrs) | Disallow to use duplicate attributes | 重複属性の禁止  |
| [@html-eslint/require-button-type](rules/require-button-type) | Require use of button element with a valid type attribute. | buttonタグのtype指定を強制 |

### SEO
Thymeleafで書かれたパーツとして利用するHTMLが多数存在する為、一律無効化とする。

### Accessibility
| rule | description | 日本語訳 |
| :--- | :---| :--- |
| [@html-eslint/require-img-alt](rules/require-img-alt) | Require `alt` attribute at `<img>` tag | imgタグでaltを必須 |
| [@html-eslint/require-frame-title](rules/require-frame-title) | Require `title` in `<frame>`, `<iframe>` | iframeタグでtitleを必須 |
| [@html-eslint/no-positive-tabindex](rules/no-positive-tabindex) | Disallow use of positive `tabindex`. | tabindexに正の値の設定を禁止 |
| [@html-eslint/no-abstract-roles](rules/no-abstract-roles) | Disallow to use of abstract roles | WAI-ARIAでの抽象ロールを禁止 |
| [@html-eslint/no-aria-hidden-body](rules/no-aria-hidden-body) | Disallow to use aria-hidden attributes on the `body` element. | aria-hiddenの利用禁止  |
| [@html-eslint/no-accesskey-attrs](rules/no-accesskey-attrs) | Disallow to use of accesskey attribute | accesskey属性の利用禁止 |

### Styles
| rule | description |  |
| :--- | :---| :--- |
| [@html-eslint/no-extra-spacing-attrs](rules/no-extra-spacing-attrs) | Disallow an extra spacing around attributes | 属性周りの余計なスペースを禁止 |
| [@html-eslint/element-newline](rules/element-newline) | Enforce newline between elements. | 要素間の改行を強制 |
| [@html-eslint/indent](rules/indent) | Enforce consistent indentation | インデントの一貫性(スペース2つとする) |
| [@html-eslint/quotes](rules/quotes) | Enforce consistent quoting attributes with double(") or single(') | 引用符の一貫性("とする) |
| [@html-eslint/id-naming-convention](rules/id-naming-convention) | Enforce consistent naming id attributes | id属性の一貫性(スネークケースとする) |
| [@html-eslint/no-multiple-empty-lines](rules/no-multiple-empty-lines) | Disallow multiple empty lines | ２行以上の改行を禁止 |
| [@html-eslint/no-trailing-spaces](rules/no-trailing-spaces) | Disallow trailing whitespace at the end of lines | 行末のスペースとタブを禁止 |

### 設定根拠
#### id属性：スネークケース
既存ソースはケバブケースが混在しているが、スネークが比較的多め
#### 引用符："
ダブルクォートの方が一般的。既存ソースに"の利用が多いため
#### インデント：スペース2つ
HTMLの場合4つの方が見やすいが、CEMS編集画面で文字数制限があり反映できない可能性が高まるため
