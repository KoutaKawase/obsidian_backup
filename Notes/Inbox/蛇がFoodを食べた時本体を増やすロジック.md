---
tags:
  - JavaScript
  - TypeScript
  - スネークゲーム
  - アルゴリズム
  - コードリーディング
  - プログラミング/実装メモ
---
#### 蛇がFoodを食べた時本体を増やすロジック
```typescript
        if (this.snake[0].x === this.food.x && this.snake[0].y === this.food.y) {
            this.snake = [...this.snake, this.snake[this.snake.length - 1]];
            this.generateFood();
        }
```
蛇の配列に一番最後と同じ座標を持つボディを追加する。
この場合、例えば
```javascript
 0: {x: 14, y: 16}
 1: {x: 14, y: 17}
 2: {x: 14, y: 18}
 3: {x: 14, y: 18}
```
こんな感じに同様のボディが最後尾に２つ連続する。

すると毎フレーム毎に[[WASDのいずれかを押した時蛇の移動を処理するロジック#unshiftとPopで移動を表現|Popされる]]ので２つのうち一つだけ消えて片方が残るのでそのまま増えたように表現できる。(頭いい)