# 落とし穴

## ネストされたコンポーネントでの Bleeding

同じエレメント名を親コンポーネントと共有するネストされたコンポーネントに気をつけてください.

```markup
<article class='article-link'>
 <div class='vote-box'>
    <button class='up'></button>
    <button class='down'></button>
    <span class='count'>4</span>
  </div>

  <h3 class='title'>Article title</h3>
  <p class='count'>3 votes</p>
</article>
```

```css
.article-link {
  > .title { /* ... */ }
  > .count { /* ... (!!!) */ }
}

.vote-box {
  > .up { /* ... */ }
  > .down { /* ... */ }
  > .count { /* ... */ }
}
```

この場合, もし `.article-link > .count` で `>` （子セレクタ）を指定されていない場合、 `.vote-box .count` 要素にも同様のルール適用されてしまいます. これが子セレクタが望ましい理由の一つです. 

