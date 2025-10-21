# Vercel へのデプロイガイド

このアプリは APIルート を使用しているため、Vercel でのデプロイを推奨します。

## 🚀 デプロイ手順

### 1. Vercel アカウントを作成

https://vercel.com にアクセスして、GitHub アカウントで Sign Up

### 2. リポジトリをインポート

1. Vercel ダッシュボードで「Add New Project」をクリック
2. GitHub リポジトリ `Hoshii` を選択
3. 「Import」をクリック

### 3. プロジェクト設定

- **Framework Preset**: Next.js（自動検出されます）
- **Build Command**: `npm run build`（デフォルトのまま）
- **Output Directory**: `.next`（デフォルトのまま）
- **Install Command**: `npm ci`（デフォルトのまま）

### 4. 環境変数を設定（必要に応じて）

Settings → Environment Variables で以下を設定：

```
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_key
```

### 5. デプロイ

「Deploy」ボタンをクリック → 数分でデプロイ完了！

## 📱 デプロイ後

- Production URL: `https://your-project.vercel.app`
- 自動プレビューデプロイ: PR ごとに自動生成
- Git プッシュで自動デプロイ: `main` ブランチへのプッシュで自動更新

## ✨ メリット

✅ APIルートが動作する
✅ サーバーサイドレンダリング（SSR）対応
✅ 画像最適化が有効
✅ 自動 HTTPS
✅ グローバル CDN
✅ 無料プラン（個人プロジェクト向け）

## 🔧 トラブルシューティング

### ビルドエラーが出る場合

1. ローカルで `npm run build` を実行して確認
2. `node_modules` を削除して `npm ci` で再インストール
3. Vercel の Build & Development Settings を確認

### Supabase 接続エラー

Environment Variables に正しい値が設定されているか確認してください。

## 📚 参考リンク

- [Vercel Documentation](https://vercel.com/docs)
- [Next.js Deployment](https://nextjs.org/docs/deployment)

