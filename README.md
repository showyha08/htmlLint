# 導入理由
HTMLは構文ミスがあっても、もしくは廃止された要素や非推奨になった要素を使ったとしても、
ページが崩れることはあるが全く表示されなくなるわけではない。
しかし、マークアップした人が意図しないデザインになった場合に、
問題が起きているタグをHTMLの中から即座に特定することは難しい。
要素が何重にも入れ子になっていたり、コードが1000行を超えていたりすると、なお問題の特定が困難になる。
そこで、Linterを導入し構文ミスに素早く気付けるようすることで、マークアップ効率を向上させることができる。
新しい仕様である『HTML Living Standard』に準拠したコードになっているか自動でチェックしてくれるため、
プロジェクト全体のHTML品質が向上する。

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

## 2.非推奨のHTMLタグやSVGコードの利用に気付ける
```
<!-- align属性は非推奨-->
<p align="center">a</p>
```

```
<!-- SVG2でversion属性は非推奨-->
<svg version="1.1" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
  <rect x="10" y="10" width="80" height="80"/>
</svg>
```

# Linterの選定について
GitHubのリポジトリからスター数が多く現在も更新が継続されている *markuplint* を選定したいと考えた。
しかし、他の方の意見を聞いてみると日本製ツールの場合メンテナンスがされなくなる可能性が高いとのこと。
たしかにGitHub上のスター数は多いが、npmjsでダウンロード数を比較すると、
eslint-plugin-html の方が圧倒的にWeeky Downloadsが多い。
![markuplint-vs-eslint-html-plugina](https://user-images.githubusercontent.com/36416614/193305365-67798816-c499-49f8-bbcc-d627422f7c0c.png)


参考：https://www.npmjs.com/package/eslint-plugin-html
参考：https://www.npmjs.com/package/markuplint

eslint-plugin-html でしかできない事は無いのか調査を行い、
markuplintと比較した後に選定することとする。

# Linter候補
## htmllint
- タスクランナー(Gulp, Grunt)、CLIで利用する静的解析ツール
- 更新:3年前
- スター：371
- https://github.com/htmllint/htmllint

## linthtml
- htmllintをForkしたツール
- Inline Configurationを使ってルールを一時的に無効化できる
- 更新:2022年9月14日
- スター：70
- https://github.com/linthtml/linthtml

## vlint
- 株式会社ミツエーリンクスが開発している日本製のツール
- W3CやWhatWGでも利用されている Nu Html Checker を利用
- https://www.npmjs.com/package/@mitsue/vlint
- https://github.com/validator/validator/

## html-eslint
- HTMLをサポートするESLintのプラグイン
- 更新:2022年6月6日
- スター:73
- https://github.com/yeonjuan/html-eslint

## markuplint
- テンプレートエンジンにも対応した静的解析ツール
- 日本人開発者が主導で開発している
- 更新:2022年9月7日
- スター：310
- https://github.com/markuplint/markuplint
- https://marketplace.visualstudio.com/items?itemName=yusukehirao.vscode-markuplint

## sonerlint
- HTMLだけでなくJavaScriptやJavaなど複数の言語に対応
- https://www.sonarlint.org/
- https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarlint-vscode
