# エレメント（Elements）

エレメントはコンポーネントの中に位置します.

![](../.gitbook/assets/image%20%281%29.png)

## エレメントの命名

それぞれのコンポーネントは0個以上のエレメントを含みます. クラス名は**一語のみ**です.

```css
.search-form {
  > .field { /* ... */ }
  > .action { /* ... */ }
}
```

## エレメントのセレクタ

可能な限り子セレクタ `>` を使います. これは子孫要素よりパフォーマンスが良く、ネストされたコンポーネントで要素の流出を防ぐことが出来るためです.

```css
.article-card {
  .title     { /* だめではない */ }
  > .author  { /* ✓ より良い */ }
}
```

## 複数語ある場合

二語かそれ以上ある場合、ダッシュやアンダースコアなしで結合します.

```css
.profile-box {
  > .firstname { /* ... */ }
  > .lastname { /* ... */ }
  > .avatar { /* ... */ }
}
```

## タグセレクタを避ける

可能な限りクラス名を使います. タグセレクタも悪くはありませんが, 多少パフォーマンスが落ちますし説明的でないです. 

```css
.article-card {
  > h3    { /* ✗ 避ける */ }
  > .name { /* ✓ 良い */ }
}
```

しかし全てのエレメントが常に同じような見た目であるべきではありません. そういった場合はバリアント（Variant）が役に立ちます. [Continue →](https://app.gitbook.com/@shufo/s/rscss/~/drafts/-LzJ1Y5OzltmnbwgEVZx/konpnentocomponents/bariantovariants) 

