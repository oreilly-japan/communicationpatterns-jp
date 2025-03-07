[> Home](https://github.com/oreilly-japan/communicationpatterns-jp) | [>特典コンテンツ](https://github.com/oreilly-japan/communicationpatterns-jp/blob/master/freebies.md)

# ADR-044 イベント駆動型アーキテクチャへの変更

## ステータス
決定済み、2023-10-04  
[ADR-031 サーバーレス関数の使用](https://link-to-superseded-ADR)を置き換える

## コンテキスト
Polyglot Mediaシステムは現在、主にサーバーレス関数からなる分散システムである。モノリシックから分散型サーバーレスアーキテクチャへ移行したのは、ライブシステムの応答性の問題や、機能とバグ修正がコード化され本番環境にデプロイされるまでの長いリードタイムに対処するためだった。

しかし、サーバーレスアーキテクチャは、応答性やメンテナンス性の問題を必要なレベルで解決しておらず、機能が他の多くの機能と強く結びついている。

応答性と市場投入までの時間の問題を解決する方法を見つける必要がある。

## 決定
イベント駆動型アーキテクチャを採用することとする。これは、高いスケーラビリティと応答性に基づいている。マイクロサービスおよびサービスベースは、最も重要な基準である応答性を十分にサポートしていない。

## 影響
### ポジティブな影響
- 現行のサーバーレス機能よりも、全体的な応答性、メンテナンス性、スケーラビリティが向上する。
- 待機中のイベントを処理するために、サービスの追加インスタンスを起動することでイベント処理のスケーラビリティが向上する。
- サービス内での処理において、サービスの追加インスタンスを起動することでスケーラビリティが向上し、サービス内での処理ニーズに対応できる。

### ネガティブな影響
- チームまたは個人が新しいスキルや技術（イベントキューなど）を学ぶ必要が出てくるかもしれない。
- イベント管理（キューなど）は、開発とデプロイメントにさらなる複雑さを加える。
- 統合テストおよびDevOpsを全面的に見直す必要が生じる。

ライセンス：[CC BY 4.0 (Jacqui Read / jacquiread.com)](https://creativecommons.org/licenses/by/4.0/)でライセンスされた[ADR-044 Change to Event-Driven Architecture](https://communicationpatternsbook.com/assets/ADR-example.html)を翻訳したものです。

[> Home](https://github.com/oreilly-japan/communicationpatterns-jp) | [>特典コンテンツ](https://github.com/oreilly-japan/communicationpatterns-jp/blob/master/freebies.md)