# すくすくメモリアル｜赤ちゃん記念日計算アプリ

生年月日を入力すると、お七夜・百日祝い・ハーフバースデー・ゾロ目記念日・七五三などを
自動計算する静的HTMLアプリです（フレームワーク不要・単一ファイル）。

## ローカルで確認する

`index.html` をブラウザでそのまま開けば動作します。ビルドは不要です。

## Vercelで公開する手順

### 1. GitHubにリポジトリを作成してpush

このフォルダのファイルをそのままGitHubリポジトリにしてください。

```bash
cd sukusuku-memorial
git init
git add .
git commit -m "Initial commit: すくすくメモリアル"
git branch -M main
git remote add origin https://github.com/【あなたのユーザー名】/sukusuku-memorial.git
git push -u origin main
```

（GitHub側で先に `sukusuku-memorial` という空のリポジトリを作成しておいてください）

### 2. Vercelにサインアップ／ログイン

https://vercel.com にアクセスし、「Continue with GitHub」でログインします
（GitHubアカウントがあればそのまま連携できます）。

### 3. プロジェクトをインポート

1. Vercelダッシュボードで **Add New → Project**
2. 先ほど作成した `sukusuku-memorial` リポジトリを選択して **Import**
3. Framework Preset は **Other**（静的HTMLのため）のままでOK
4. Build Command・Output Directory は空欄のままでOK（`index.html` がルートにあるため自動検出されます）
5. **Deploy** をクリック

数十秒で `https://sukusuku-memorial-〇〇〇.vercel.app` のようなURLが発行されます。

### 4. 公開後にやること

1. 発行されたURLを教えてください。`index.html` 内の以下の箇所を実URLに差し替えます（私の方で対応可能です）。
   - `<link rel="canonical" ...>`
   - `og:url`
   - JSON-LD構造化データ内のURL
2. Google Search Console（https://search.google.com/search-console）にURLを登録し、インデックス登録をリクエスト
3. 以後、GitHubに `git push` するだけで自動的に本番URLへ再デプロイされます

## ファイル構成

```
sukusuku-memorial/
├── index.html   ← アプリ本体（このファイルのみで完結）
└── README.md    ← このファイル
```
