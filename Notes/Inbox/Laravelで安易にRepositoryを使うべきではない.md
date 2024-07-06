---
tags:
  - Laravel/アンチパターン
  - Laravel/設計
  - プログラミング/DDD
  - プログラミング/設計
  - プログラミング/アンチパターン
  - プログラミング/Laravel
---

- [[Laravel]]で安易に[[Repository]]パターンを使うのは避けるべき
- [[Active_Record]]Recordで[[Repository]]パターンを採用するのは[[Active_Record]]の良さを殺してしまうことが多い
- 何より[[Repository]]パターンが何かを不勉強であるのに使用するのは危険。エセ[[Repository]]パターンになる
[https://twitter.com/n\_1215/status/1677490188690554880](https://twitter.com/n_1215/status/1677490188690554880)

>私は別に Repository の実装に ActiveRecord 居てもいいと思いますけどね　返り値や引数から漏れずに内部的に使うだけなら
>[https://twitter.com/mpyw/status/1677508393962196992](https://twitter.com/mpyw/status/1677508393962196992)

こういう意見もある🤔

>スタートがActiveRecordを使うCRUDだからそこからの類推で勘違いはしやすいのか 元のCRUDコントローラから単にDBクエリを呼んでる部分をクラスに切り離したのがRepositosyかな、くらいの解釈に陥る そこにネットに溢れる大量のRepositoryパターンもどきの情報をぶち込んでやるとあら不思議ってか
[https://twitter.com/n\_1215/status/1677503151661023232](https://twitter.com/n_1215/status/1677503151661023232)

- [[Repository]]パターンの実装に不適切なモノが多いのは[[集約]]の理解が浅いかららしい。
	- つまりDDDをしっかり勉強するべき
>リポジトリの実装は不適切なものが多い。集約の理解がないから失敗する。リポジトリの中で集約を跨いだI/Oをしたり、そもそも集約の一部だけを書き込んだりと。不勉強ならまだORMそのまま使った方がよかったのにという事例もある。リポジトリを正しく設計するには集約が何かを理解してないと難しい。
>[https://twitter.com/j5ik2o/status/1677497751838543873](https://twitter.com/j5ik2o/status/1677497751838543873)