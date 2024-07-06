---
tags:
  - JavaScript
  - TypeScript
  - スネークゲーム
  - アルゴリズム
  - コードリーディング
  - プログラミング/実装メモ
---

#### WASDのいずれかを押した時蛇の移動を処理するロジック 
```TypeScript
public start(): void {
	this.moveTimeout = setInterval(() => this.move(), this.moveInterval);
    window.addEventListener('keydown', (event) => this.handleKeyDown(event));
    this.#isRunning = true;
}
```
まずグローバルのkeydownイベントでWASD入力を拾っている。

```typescript
    private handleKeyDown(event: KeyboardEvent): void {
        switch (event.key) {
            case 'w':
                if (this.direction !== 'down') {
                    this.direction = 'up';
                }
                break;
            case 's':
                if (this.direction !== 'up') {
                    this.direction = 'down';
                }
                break;
            case 'a':
                if (this.direction !== 'right') {
                    this.direction = 'left';
                }
                break;
            case 'd':
                if (this.direction !== 'left') {
                    this.direction = 'right';
                }
                break;
        }
    }
```
例えば右に進んでる時に左に入力して左に動いてしまうのは避けたいので、蛇が進んでる方向を
direction変数として状態を保持して、入力した方向に対して現在進んでる方向がその反対ではないことをチェックしている。

```TypeScript
this.moveTimeout = setInterval(() => this.move(), this.moveInterval);
```

とあるようにmove()がいわゆるUpdate関数でメインループとなる

```TypeScript
        const head = {
            ...this.snake[0]
        };
        switch (this.direction) {
            case 'up': head.y -= 1;
                break;
            case 'down': head.y += 1;
                break;
            case 'left': head.x -= 1;
                break;
            case 'right': head.x += 1;
                break;
        }
        this.snake.unshift(head);
        this.snake.pop();

```

### unshiftとPopで移動を表現

メインループ内で(毎フレームごとに実行される関数)で先頭のコピーを取得して、現在のダイレクションを元にその方向に1座標分、先頭座標をズラす。

ズラした先頭をunshift()で先頭に挿入、一番後ろのボディを削除して移動を表現している。

□□□　→　□□□□　→ □□□ 