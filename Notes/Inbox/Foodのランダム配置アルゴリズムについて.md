---
tags:
  - JavaScript
  - TypeScript
  - スネークゲーム
  - アルゴリズム
  - コードリーディング
  - プログラミング/実装メモ
---
### Foodのランダム配置アルゴリズムについて
```typescript
const food = { 
	x: Math.floor(Math.random() * (CANVAS_SIZE/BLOCK_SIZE)),
	y: Math.floor(Math.random() * (CANVAS_SIZE/BLOCK_SIZE))
};
```
こんな感じでランダム配置を決定している。

まずCANVAS_SIZE(400)をBLOCK_SIZE(10)で割ってBLOCK_SIZE一つの大きさで何個入るのかを計算している。
この場合BLOCK_SIZEのRectangleが40個入ることになる。
これにrandom()ででる0以上1未満の数値をかけてMath.floorで余分なぶんを切り捨てている。

この
```javascript
Math.floor(Math.random() * (CANVAS_SIZE/BLOCK_SIZE)
```
で出る数値は座標の直接の数値ではなく、何番目の箇所を指しているか。
40個BLOCK_SIZEの箱が入るので0番目から40番目のどれに該当するか。

つまり8番目ならBLOCK_SIZE８個分なので座標に直すときは
```typescript
	const x = point.x * blockSize;
	const y = point.y * blockSize;
```
みたいに掛け算して座標を計算する必要がある。