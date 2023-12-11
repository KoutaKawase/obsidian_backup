---
tags: Laravel セキュリティ 認証 JWT
---

### JWTをセッショントークンとして使用してはいけない
> Web アプリに ID プロバイダーを使用する場合は、JWT を使用してユーザーを識別し、検証します。
> その後、検証されたユーザー情報を使用してセッションを確立することで、Cookie 認証移行できます (JWT を Cookie に直接保存しません)。

[Best Practices for Using JWT. 5 Best Practices to Follow When Using… | by Piumi Liyana Gunawardhana | Bits and Pieces](https://blog.bitsrc.io/best-practices-for-using-jwt-df3788433fd3)

Firebase Auth等でユーザーを検証したらバックエンドフレームワーク側で従来のセッションを開始するのがいいっぽい。
[JWT Token Security Best Practices | Curity](https://curity.io/resources/learn/jwt-best-practices/#13-do-not-use-jwts-for-sessions)
> JWT はセッションで使用することは考慮されていないため

[JWT authentication: Best practices and when to use it - LogRocket Blog](https://blog.logrocket.com/jwt-authentication-best-practices/)
>JWT を無効にする中央の権限がないため、セッションの終了時に削除できない
- セッションクッキーならバックエンドでセッションIDを削除するだけで済む

> 最終的に、アプリケーション用のデータベースがすでにある場合は、セッション テーブルを使用し、選択したサーバー側フレームワークによって提供される通常のセッションを使用するだけです

[[SPA等のWebフロントでセッションCookieは悪ではない]]


