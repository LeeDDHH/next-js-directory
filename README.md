# Next.js のディレクトリ構成について

## 前提

- `next.js` のバージョンは 12 を想定

## 構成

```markdown
.
├── components
│ 　 ├── elements
│ 　 │ 　 └── utils
│ 　 ├── layouts
│ 　 └── page
├── config
├── const
├── docs
├── hooks
├── libs
├── pages
├── public
├── stores
├── test
├── types
└── utils
　　 ├── api
　　 │ 　 ├── del
　　 │ 　 ├── get
　　 │ 　 ├── post
　　 │ 　 └── put
　　 └── auth
```

### components

- アプリケーション全体で使うコンポーネントを置く
- `components/elements`
  - `components/layouts` と `components/page` で使うコンポーネントを置く
- `components/elements/utils`
  - アプリケーション全体で使う共通コンポーネントを置く
- `components/layouts`
  - アプリケーション全体で使うレイアウトコンポーネントを置く
  - Header・Footer・管理者や一般ユーザーなどによってレイアウトを出し分ける Layout コンポーネントを置く
- `components/page`
  - `components/elements` と `components/layouts` を組み合わせたコンポーネントを置く
  - `pages` からは `components/page` のコンポーネントを読み込むだけ使える形にしたものを置く

### config

- アプリケーション全体の設定を置く
- 主に CSS フレームワークの設定やライブラリの設定などを置く

### const

- アプリケーション全体の定数を置く

### docs

- 開発時の注意事項、アイデアを置く

### hooks

- react のカスタムフックを置く

### libs

- ライブラリ固有のコード、ラッパー、初期化や設定のコードなど、データ取得に絡まないコードを置く
- ライブラリ毎に切り替わる可能性もあるので、ライブラリごとにディレクトリを分ける

### pages

- Next のページコンポーネントを置く

### public

- 静的ファイルを置く

### stores

- アプリケーション全体のグローバルステート、データフェッチライブラリの管理に使う設定を置く

### test

- テストコードを置く

### types

- type、interface を置く

### utils

- グローバルで使える関数を置く
- `utils/api`
  - HTTP リクエストを置く
  - 必要であれば、各 HTTP リクエストディレクトリの中をページごとにディレクトリを分ける
- `utils/auth`
  - 認証系の処理を置く

## 参考

- [Next.js ディレクトリ構成・設計再考（features が何を解決するか）](https://zenn.dev/yodaka/articles/eca2d4bf552aeb)
- [Setup TypeScript with React | React TypeScript Cheatsheets](https://react-typescript-cheatsheet.netlify.app/docs/basic/setup/)
- [alan2207/bulletproof-react: 🛡️ ⚛️ A simple, scalable, and powerful architecture for building production ready React applications.](https://github.com/alan2207/bulletproof-react)
- [Next.js のディレクトリ構成を考えてみた](https://zenn.dev/mongolyy/articles/01f0a4375edb2e)
- [Nextjs プロジェクトのディレクトリ構成例をさらしてみる - Qiita](https://qiita.com/kentt/items/c86782b481ec175a57e2)
- [Next.js 導入で責務の所在を明確化　 READYFOR のフロントエンド分離戦略 - ログミー Tech](https://logmi.jp/tech/articles/324137)
