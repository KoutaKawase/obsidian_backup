---
tags:
  - プログラミング/Laravel
  - プログラミング/設計
---
## Viewから極力Modelを触らない
### なぜModelではダメなのか

Eloquent Model をそのまま使わず、Viewに渡すデータはすべて`Entity`に変換するようにした理由はこちらです。

- APIから取得したデータも同じように扱いたい
    
- Modelクラスにはテーブルのリレーションなどの情報も定義する必要があり、また Eloquent Model を継承しているので、新たに表示用のロジックを追加するとなると責任過多になる
    
- チームが Active Record の扱いに慣れていないので、ViewでModelを使うとN+1問題が多発する

```
ここで簡単に、N+1問題について例示します。  
Eloquent Model の Collection（配列）を取得する際に、[Eagerロード](https://readouble.com/laravel/8.x/ja/eloquent-relationships.html#eager-loading)しておかないと下記のように１回（Itemsの取得）+ N回（各ループでのShopの取得）のクエリが実行されます。  
ちなみに、Eagerロードをすると１回（Itemsの取得）+ １回（Itemsのshop_idに紐づくShopsの取得）の計２回のクエリで済みます。
```

[Site Unreachable](https://jqiita.com/yiwiy9/items/121fe0e73279687261b8)