# ヘルパー（Helpers）

値をオーバーライドすることが目的の汎用クラスは別のファイルに分け、アンダースコアで始まる名前にしてください. それらのクラスは大抵 _!important_ 属性が付与されますが気をつけて使用してください. 

```css
._unmargin { margin: 0 !important; }
._center { text-align: center !important; }
._pull-left { float: left !important; }
._pull-right { float: right !important; }
```

## ヘルパーの命名

クラス名のプリフィックスにアンダースコアを付与してください. これはコンポーネントで定義されたmodifierと区別するのに役立ちます. アンダースコアはあまり見栄えは良くないですがこれは意図した副作用です. つまりヘルパーの多用は推奨されないということです.

## ヘルパーの管理

全てのヘルパーを `helpers`という一つのファイルで管理してください. 複数のファイルに分けることも出来ますが, ヘルパーを必要最小限に保っておくことが望ましいためです.



