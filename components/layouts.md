# レイアウト（Layouts）

![.recipe-list&#x3068;&#x3044;&#x3046;&#x30EC;&#x30A4;&#x30A2;&#x30A6;&#x30C8;&#x3068;.recipe-item&#x30B3;&#x30F3;&#x30DD;&#x30FC;&#x30CD;&#x30F3;&#x30C8;](../.gitbook/assets/image%20%284%29.png)

## 位置指定プロパティを避ける

コンポーネントは異なるコンテキストで再利用可能なように作られるべきです. なので以下のようなプロパティをコンポーネントで指定することは避けてください.

* 位置指定（`position`, `top` , `left` , `right` , `bottom`）
* Floats \(`float` , `clear` \)
* マージン\(`margin`\)
* 寸法\(`width` , `height`\)

## 固定サイズ

ただしアバターやロゴのような固定サイズの要素は例外として扱うことが出来ます.

## 親要素で位置指定する

もし位置指定が必要な場合その要素が存在するコンテキストで定義してみてください.  下記の例でコンポーネントそれ自体ではなく、リストコンポーネントにwidthとfloatが適用されているように.

```css
.article-list {
  & {
    @include clearfix;
  }

  > .article-card {
    width: 33.3%;
    float: left;
  }
}

.article-card {
  & { /* ... */ }
  > .image { /* ... */ }
  > .title { /* ... */ }
  > .category { /* ... */ }
}
```

レイアウトの外のマージンを指定するにはどうしたらいいでしょう？ヘルパーでやってみましょう [Continue →](https://app.gitbook.com/@shufo/s/rscss/~/drafts/-LzJ1Y5OzltmnbwgEVZx/konpnentocomponents/heruphelpers)

