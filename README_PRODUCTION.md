# 本番配布メモ

このアプリは静的サイトです。`dist` フォルダ内の以下をそのまま本番環境へ配置してください。

- `dist/index.html`
- `dist/assets/map.jpg`

サーバー設定は特別なビルド処理を必要としません。HTTPS の静的ホスティング、社内サーバー、GitHub Pages などに `dist` の中身をアップロードすれば動作します。

ローカル確認は `dist/index.html` をブラウザで開くか、任意の静的ファイルサーバーで `dist` を配信してください。

## GitHub Pages で公開する場合

このリポジトリには `.github/workflows/pages.yml` を追加済みです。GitHub に push すると、`dist` フォルダの内容が GitHub Pages にデプロイされます。

GitHub 側では以下を確認してください。

1. リポジトリの `Settings` を開く
2. `Pages` を開く
3. `Build and deployment` の `Source` を `GitHub Actions` にする
4. `main` または `master` ブランチへ push する
5. `Actions` タブで `Deploy static site to GitHub Pages` が成功したら公開URLが表示されます

`git` と GitHub CLI が使える環境なら、初回公開は以下の流れです。

```powershell
git add .
git commit -m "Prepare crossword app for GitHub Pages"
git branch -M main
git remote add origin https://github.com/<USER>/<REPO>.git
git push -u origin main
```
