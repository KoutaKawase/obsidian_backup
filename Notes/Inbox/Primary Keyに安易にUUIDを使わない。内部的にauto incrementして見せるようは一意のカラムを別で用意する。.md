---
tags:
  - プログラミング/設計
  - プログラミング/DB
---
## ユーザーに見えるUIに出てくるIDは常に乱数ベースのpublic_idを使う
[データベースでユニークキーにUUIDを使うメリットは何ですか？連番やタイムスタンプまたは複合などではいけないのでしょうか？どうも視認性が悪く使いにくく感じますし連番でも衝突しない気もします。 - Quora](https://jp.quora.com/%E3%83%87%E3%83%BC%E3%82%BF%E3%83%99%E3%83%BC%E3%82%B9%E3%81%A7%E3%83%A6%E3%83%8B%E3%83%BC%E3%82%AF%E3%82%AD%E3%83%BC%E3%81%ABUUID%E3%82%92%E4%BD%BF%E3%81%86%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88%E3%81%AF%E4%BD%95)

UUIDは[「参照の局所性」（Locality of Reference）](https://ja.wikipedia.org/wiki/%E5%8F%82%E7%85%A7%E3%81%AE%E5%B1%80%E6%89%80%E6%80%A7 "ja.wikipedia.org")というコンピューターサイエンス最強の武器を殺してしまう

## ただしUUID v7 あるいはPostgreSQLのネイティブUUIDはパフォーマンスがいいらしい

## ユーザーに見せる用はSqidsを使う 
