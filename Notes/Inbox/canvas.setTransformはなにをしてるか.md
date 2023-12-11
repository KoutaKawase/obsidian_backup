---
tags: JavaScript TypeScript フロントエンド Canvas
---
### canvas.setTransformはなにをしてるか
[CanvasRenderingContext2D: setTransform() method - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/setTransform)
>If a point originally had coordinates (x,y), then after the transformation it will have coordinates (ax+cy+e,bx+dy+f). This means:

つまり

```javascript
const snakeConstatns.SCALE = 40;
ctx.setTransform(snakeConstatns.SCALE, 0, 0, snakeConstatns.SCALE, 0, 0);
```
みたいなコードはxに入力された数値を40倍してyに入力された数値が40倍されるということ

```javascript
ctx.fillRect(8, 8, 1, 1); // = ctx.fillRect(320, 320, 40, 40)と同じ