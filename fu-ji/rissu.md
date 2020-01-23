# リソース

* [ITCSS](https://speakerdeck.com/dafed/managing-css-projects-with-itcss#49) \("Inverted Triangle CSS"\) はrscss構造を補完するのに良い方法です
* [rsjs](http://ricostacruz.com/rsjs/) \("Reasonable Standard of JavaScript Structure"\) はベーシックなサイトでJavaScriptを構築するためのドキュメントです（WIP）

## 他のソリューション

[BEM](http://bem.info/) は良いですが、この不可解なシンタックスが嫌な人もいるかもしれません. RSCSS はBEMの規約にとても影響を受けていますが、異なるのはシンタックスのみです.

```markup
<!-- BEM -->
<form class='site-search site-search--full'>
  <input  class='site-search__field' type='text'>
  <button class='site-search__button'></button>
</form>
```

```markup
<!-- rscss -->
<form class='site-search -full'>
  <input  class='field' type='text'>
  <button class='button'></button>
</form>
```

## 用語集

同じような概念が他のCSS設計にも存在します. 

| RSCSS | BEM | SMACSS |
| :--- | :--- | :--- |
| Component | Block | Module |
| Element | Element | Sub-Component |
| Layout | ? | Layout |
| Variant | Modifier | Sub-Module & State |



