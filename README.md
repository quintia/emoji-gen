# emoji-gen (mini)

[絵文字ジェネレーター](https://emoji-gen.ninja/) を参考にした、最小機能のスタンドアロン絵文字ジェネレーターです。
`index.html` 1 ファイルだけで動き、サーバーは不要です。

## 使い方

`index.html` をブラウザで開き、テキストを入力して「生成する♪」を押すと 128×128 の透過 PNG が生成されます。
画像は右クリックで保存できます。

フォントは Google Fonts から読み込むため、インターネット接続が必要です。

## 機能

- **テキスト**: 改行で複数段にできます。各段は高さを等分し、文字の実寸が段の高さいっぱいになるよう描画されます。幅を超える段は横方向に圧縮されます。
- **文字揃え**: 左 / 中央 / 右。幅に余裕がある段の配置に効きます。
- **文字幅を最小の段に揃える**: 最も強く横圧縮された段の圧縮率を全段に適用し、文字の縦横比を揃えます。
- **フォント**: 3 種類から選べます。
  | 表示名 | Google Fonts |
  |---|---|
  | Noto Sans JP Bold | Noto Sans JP 700 |
  | M+ 1p black | M PLUS 1p 900 |
  | Rounded M+ black | M PLUS Rounded 1c 900 |
- **色**: 2 段のプリセットパレットと、任意の色を選べるカラーピッカーがあります。背景は常に透過です。
  - 1 段目: ライト・ダークどちらの背景でもコントラスト比 3:1 以上の中間色
  - 2 段目: 1 段目を明るくした色（ライト背景で約 2.3:1、ダーク背景で約 7.4:1）
- **プレビュー**: 透過の原寸表示に加えて、Slack 風のライト / ダーク背景で、メッセージ内 (22px) とリアクション (16px) のサイズで表示します。

## カスタマイズ

`index.html` の `<script>` 内で次の定数を編集します。

- `PALETTE`: プリセット色（1 要素が 1 段）
- `FONTS`: フォントの選択肢（`css` は CSS の `font` プロパティ値。`{px}` がサイズに置換されます）

## 謝辞

UI と描画の挙動は [絵文字ジェネレーター](https://emoji-gen.ninja/)（[emoji-gen/emoji-generator](https://github.com/emoji-gen/emoji-generator)）を参考にしています。
コードは流用しておらず、本プロジェクトは同サービスとは無関係です。

フォントはいずれも SIL Open Font License 1.1 のもとで Google Fonts から配信されるものを利用しています。

## License

Copyright (C) 2026 K Yamaguchi

参考元の [emoji-gen/emoji-generator](https://github.com/emoji-gen/emoji-generator) に倣い、[GNU General Public License v3.0](LICENSE) で公開します。
