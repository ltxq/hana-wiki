# Gemini API キーの取得方法

このガイドでは、**サーバー専属秘書デスク（`/hanacontext`）** や **NPC ロールプレイシステム（`/npc`）** で利用するための Google Gemini API キーを約2〜3分で取得する手順を解説します。

> ⚠️ **セキュリティ警告:** API キーはパスワードと同等の機密情報です。公開チャットに投稿したり、他者と共有したり、キー全体が映ったスクリーンショットを共有しないでください。誤って流出した場合は、直ちに Google AI Studio で該当キーを削除して再作成してください。

---

## 1. Google AI Studio にアクセス

[Google AI Studio](https://aistudio.google.com/welcome) にアクセスし、個人の Google アカウントでログインします。

初めて利用する場合は **Get started** をクリックし、Google の利用規約に同意してください。

![Google AI Studio の Get started ボタン](../.gitbook/assets/gemini-api-key-01-get-started.png)

---

## 2. API Keys ページを開く

AI Studio ダッシュボードに入ったら、左側のサイドメニューにある鍵マークの **API Keys** アイコンをクリックします。

![API Keys ページを開く鍵マーク](../.gitbook/assets/gemini-api-key-02-menu.png)

---

## 3. API キーを作成

**Create API Key** ボタンをクリックします。

![Create API Key ボタン](../.gitbook/assets/gemini-api-key-03-create.png)

- 新規アカウントの場合、初期プロジェクトとキーがあらかじめ生成されていることがあります。その場合はそのキーをコピーしてそのまま使用できます。
- プロジェクトの選択画面が表示された場合は、既存の Google Cloud プロジェクトを選ぶか、新規プロジェクトを作成してください。
- 作成されたら **Copy** アイコンをクリックしてキーを安全な場所にコピーします。

---

## 4. Hana に API キーを登録する

### サーバー専属秘書デスク（`/hanacontext`）の場合
1. Discord サーバーで `/hanacontext` を実行します。
2. `ChannelSelectMenu` から秘書を配属したいチャンネルを選択します。
3. **「秘書設定 / 編集」** ボタンをクリックします。
4. **Gemini API Key** 欄にコピーしたキーを貼り付けて送信します。
5. キーの有効性が検証され、Bot 本体のクォータを消費することなく秘書機能が即座に利用可能になります。

### NPC ロールプレイ（`/npc`）の場合
- サーバーで設定された共有キーや割り当てキーを使用して、ホストの制限に縛られずに快適なロールプレイ応答を利用できます。

---

## 注意事項とトラブルシューティング

- 学校や企業の組織向け Google Workspace アカウントでは、API キーの発行が制限されている場合があります。個人の通常 Google アカウントをご利用ください。
- Hana に入力された API キーは、データベース保存前に **AES-256-GCM により強力に暗号化** されます。ログや出力に平文で記録されたり外部に漏洩することはありません。
- 公式 Google ドキュメント: [Gemini API はじめに](https://ai.google.dev/gemini-api/docs/get-started) · [API キーの管理](https://ai.google.dev/gemini-api/docs/api-key)
