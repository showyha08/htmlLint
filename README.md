# 導入理由
HTMLは構文ミスがあっても、もしくは廃止された要素や非推奨になった要素を使ったとしても、
ページが崩れることはあるが全く表示されないわけではない。
しかし、作成者が意図しない表示になった場合に、問題が起きているタグをHTMLの中から見つけることは容易ではない。
要素が何重にも入れ子になっていたり、1000行を超えたりするとなお問題の特定が困難になる。
そこで、Linterを導入し構文ミスに素早く気付けるようすることで、マークアップの効率を向上させることができるとともに
HTML5の仕様に準拠したコードを書くことができる。

## 1.HTMLの構文ミスに気付ける
```
<!-- 例：liタグを未定義-->
<!-- この場合デフォルトのlistのデフォルトスタイルがあたらない-->
<ul>
  <a ref="https://www.google.com/">google</a>
</ul>

<!-- liタグを定義-->
<ul>
  <li>
    <a href="https://www.google.com/">google</a>
  </li>
</ul>
```

## 2.非推奨タグの利用に気付ける
```
<!-- alignタグはHTML5で非推奨-->
<p align="center">a</p>
```

# HTML用のLinter候補
スター数も多く現在も更新が継続されている *markuplint* を選定したい。

## htmllint
- タスクランナー(Gulp, Grunt)、CLIで利用する静的解析ツール
- 更新:3年前
- スター：371
- https://github.com/htmllint/htmllint

## html-eslint
- HTMLをサポートするESLintのプラグイン
- 更新:2022年6月6日
- スター:73
- https://github.com/yeonjuan/html-eslint

## markuplint
- テンプレートエンジンにも対応した静的解析ツール
- 更新:2022年9月7日
- スター：310
- https://github.com/markuplint/markuplint
- https://marketplace.visualstudio.com/items?itemName=yusukehirao.vscode-markuplint


