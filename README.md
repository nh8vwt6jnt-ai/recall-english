# Recall English PWA

完全無料・オフラインで使う個人用英語学習PWAです。

## できること
- iPhoneホーム画面からアプリ風に起動
- 復習期限・A/B/C・正誤をローカル保存
- 復習優先で「今日のLesson」を自動生成
- 分野選択（基礎 / 会議 / 仕事 / 旅行 / データセンター / 文法）
- ローカル解説
- 解説不足・繰り返し誤答時に「GPTに聞く」導線
- 全学習データをGPTへ渡すためのコピー
- GPTから返された `recall_english_patch` JSONを既存履歴に統合
- JSONバックアップ / 復元
- オフラインキャッシュ

## iPhoneで使う
PWAとしてインストールするには HTTPS で公開する必要があります。
無料の GitHub Pages などにこのフォルダの中身をそのまま公開し、
iPhone Safariで開いて「共有」→「ホーム画面に追加」を使ってください。

## GPTからアプリへ戻すJSON形式
```json
{
  "type": "recall_english_patch",
  "items": [
    {
      "id": "P0100",
      "ja": "例文",
      "en": "Example.",
      "category": "会議",
      "type": "表現",
      "explanation": "短い解説"
    }
  ],
  "progress": [],
  "history": [],
  "settings": {}
}
```

既存IDを同じIDで返すと、その項目の解説等を更新します。

## Public-safe版について
この版の `index.html` には個人のLesson履歴、A/B/C実績、Weak Items、過去の誤答記録を初期データとして含めていません。
学習を開始した後の進捗は端末側の localStorage に保存されます。
一般教材（基礎・会議・仕事・旅行・データセンター・文法）はアプリ本体に含まれます。
