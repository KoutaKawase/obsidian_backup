---
tags: Next.js Remix フロントエンド BFF 設計 CORS
---
### Next.jsやRemix.runのAPI機能はBFFとして使える
[How Remix scales : r/reactjs](https://www.reddit.com/r/reactjs/comments/14m5fju/how_remix_scales/)
>個人的には、これらの React フルスタック フレームワークは、専用バックエンドへのプロキシとして最適に機能すると思います。つまり、専用バックエンドは API を Remix/Next などに公開します。フレームワークは API の応答を使用してページの構築を支援します。これにより、[[CORS]] の問題が軽減され、セキュリティが向上します。

RemixなどのAPI機能は[[BFF]]として使うと[[CORS]]の悩みが消えるかも🤔

[Backend For Frontend | Remix](https://remix.run/docs/en/main/guides/bff)
Remix公式もBFFを推奨している。
