# CSS Structure

## 一つのコンポーネントにつき一つのファイル

それぞれのコンポーネントをそれ自身のファイルに置いてください.

```css
/* css/components/search-form.scss */
.search-form {
  > .button { /* ... */ }
  > .field { /* ... */ }
  > .label { /* ... */ }

  // variants
  &.-small { /* ... */ }
  &.-wide { /* ... */ }
}
```

## glob パターンマッチを使用する

sass-railsやstylusでは全てのファイルをincludeするのにこれが簡単です.

```css
@import 'components/*';
```

## 過剰なネストを避ける

1レベル以上のネストは避けましょう. ネストのしすぎは簡単に現在位置を見失います.

```css
* ✗ 避けるべき: 3 レベルのネスト */
.image-frame {
  > .description {
    /* ... */

    > .icon {
      /* ... */
    }
  }
}

/* ✓ 良い: 2 レベルのネスト */
.image-frame {
  > .description { /* ... */ }
  > .description > .icon { /* ... */ }
}
```

