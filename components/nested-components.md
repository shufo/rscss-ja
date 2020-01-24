# ネストされたコンポーネント \(Nested Components\)

![.article-link&#x306B;&#x30CD;&#x30B9;&#x30C8;&#x3055;&#x308C;&#x305F;.vote-box&#x30B3;&#x30F3;&#x30DD;&#x30FC;&#x30CD;&#x30F3;&#x30C8;](../.gitbook/assets/image%20%283%29.png)

```markup
<div class='article-link'>
  <div class='vote-box'>
    ...
  </div>
  <h3 class='title'>...</h3>
  <p class='meta'>...</p>
</div>
```

このようにコンポーネントをネストする必要が出てくる場合があります. ここでいくつかの方法を紹介します. 

## バリアント \(Variants\)

コンポーネントは別のコンポーネントでネストされた時に特定の方法で表現する必要がある場合があります. ネストされたコンポーネントを修正しないようにするにはそれを含むコンポーネントからアクセスします.

```css
.article-header {
  > .vote-box > .up { /* ✗ これは避ける */ }
}
```

代わりに, ネストされたコンポーネントにバリアントを加えてそれを含むコンポーネントから適用した方が良いです.

```markup
<div class='article-header'>
  <div class='vote-box -highlight'>
    ...
  </div>
  ...
</div>
```

```css
.vote-box {
  &.-highlight > .up { /* ... */ }
}
```

## ネストされたコンポーネントをシンプルにする

コンポーネントをネストしたとき、マークアップが美しくなくなる時があります.

```markup
<div class='search-form'>
  <input class='input' type='text'>
  <button class='search-button -red -large'></button>
</div>
```

こういった場合はCSSプリプロセッサの`@extend`を使ってシンプルにすることが出来ます.

```markup
<div class='search-form'>
  <input class='input' type='text'>
  <button class='submit'></button>
</div>
```

```css
.search-form {
  > .submit {
    @extend .search-button;
    @extend .search-button.-red;
    @extend .search-button.-large;
  }
}
```

リストのようにエレメントを繰り返したい場合はどうしたらよいでしょう。次のレイアウトで見てみます [Continue →](https://app.gitbook.com/@shufo/s/rscss/~/drafts/-LzJ1Y5OzltmnbwgEVZx/konpnentocomponents/reiautolayouts)

