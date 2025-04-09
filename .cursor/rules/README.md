# .cursor/rules

## モード

以下のモードが定義されています。

- `Plan`: 実装計画の作成や、設計の立案に適したモード
  - コンテキストウィンドウサイズが大きくなるため、Gemini 2.5 Proなどの大きなサイズを持つモデルを使用してください。
- `Act`: コードの実装を行うモード
  - コード実装そのものを行うため、Claude 3.7 Sonnetなどの高性能でより実装に向いたモデルを使用してください。
- `Debug`: デバッグやテストの実行を行うモード

## Acknowledgment

このルールを作成するにあたり、以下を参考にさせていただきました。

- [AIを用いた開発の効率を最大化させるためにやっていることを全部書く](https://zenn.dev/ks0318/articles/4b201527b383fa)
- [ks0318-p/Cursor-Project-Rules](https://github.com/ks0318-p/Cursor-Project-Rules)
- [mizchi/ailab](https://github.com/mizchi/ailab)
