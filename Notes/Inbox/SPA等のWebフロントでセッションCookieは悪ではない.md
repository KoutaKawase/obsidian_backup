---
tags: Laravel セキュリティ 認証 JWT
---

### SPA等のWebフロントでセッションCookieは悪か？

[トークンと Cookie を併用することが Web アプリのセキュリティに優れている理由](https://blog.bitsrc.io/why-using-tokens-and-cookies-together-is-better-for-web-apps-9d205b7c1961)
>Web アプリとモバイル アプリの場合は、 Web アプリケーションの問題をモバイル アプリなどから分離する[BFF パターン](https://samnewman.io/patterns/architectural/bff/)の使用をお勧めします。

>Web バックエンドを Web アプリケーション専用にしておけば、Cookie についての疑いは簡単に消えます

- WebフロントエンドがSPAのようなものでもCookieは使って良い。
- モバイルなど純粋なWeb APIも必要ならBFFパターンを使う
>現時点でお勧めできる最善のアプローチは、JWT と Cookie の両方を組み合わせて使用​​することです


実際PixivもWebフロントを覗くと**PHPSESSID**がある

[Web アプリのバックエンドは API ではありません。それに直面しよう！](https://blog.bitsrc.io/your-web-app-backend-is-not-an-api-lets-face-it-5b8d738458a6)

> JSON を提供するバックエンドは必ずしも API である必要はありません

- LaravelだとWebとAPIでRouteを分けられるが、JSONを返すからといって必ずしもAPI Routeを使わなくて良い。
- つまりCookieなどWeb向けならば使っても良いのだ！

>Web アプリのバックエンドとは対照的に、API に重大な変更があった場合、ユーザーの携帯電話でモバイル アプリのバージョンを直接更新できないため、モバイル バックエンドを API として構築することは理にかなっています。したがって、モバイル アプリのバージョンが異なれば、その操作には異なる API バージョンが必要になります。サードパーティの統合にも同じことが当てはまります。API を変更するほど、サードパーティはすぐに変更を加えることはありません。ここでは、さらなる制御とガバナンスが必要です。したがって、モバイル アプリとサードパーティの統合には、別の API を開発することが合理的です。

- だからv1とかv2とかがついてたりするのか🤔
- Webフロントはモバイルのように直接更新できないわけではない

