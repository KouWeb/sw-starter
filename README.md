# sw-starter

TypeScript・SCSSのコンパイル、ローカル開発サーバーに加え、各種Lintを備えた静的Webサイト制作用の開発環境テンプレートです。

---

## セットアップ

1.  プロジェクトをVSCodeで開きます。以下のいずれかでプロジェクトを開いてください。
    -	プロジェクトルートフォルダをVSCodeで開く。
	-	プロジェクトルートにある`workspace.code-workspace`をダブルクリックで開く。

2.  必要な拡張機能をインストールします。  
    画面右下の通知に表示される推奨拡張機能をインストールします。

    通知が表示されなかったり閉じてしまった場合は、拡張機能の検索で`@recommended`を検索し、ワークスペースの推奨事項に表示される拡張機能をすべてインストールしてください。

3.  必要なパッケージをインストールします。  
    プロジェクトルートで以下のコマンドを実行します。

    ```
    npm install
    ```

4.  以下のコマンドを実行して、ブラウザが立ち上がればセットアップ完了です。

    ```
    npm run watch
    ```

---

## 開発を始める

### テンプレート製作者向け

以下のコマンドを実行すると、開発に必要なすべての処理が起動します。

```bash
npm run watch
```

起動すると以下が自動で行われます。

- TypeScript（`src/_ts/`）の監視・コンパイル
- SCSS（`src/_scss/`）の監視・コンパイル
- ローカルサーバーの起動とブラウザの自動リロード

ブラウザが自動で開き、`src/index.html` が表示されます。ファイルを保存するたびにブラウザが自動でリロードされます。

開発を終了するときはターミナルで `Ctrl + C` を押してください。

---

### HTMLコーダー向け

以下のコマンドを実行すると、ブラウザ自動更新が起動します。

```bash
npm run watch:bs
```

起動すると以下が自動で行われます。

- ローカルサーバーの起動とブラウザの自動リロード

ブラウザが自動で開き、`src/index.html` が表示されます。ファイルを保存するたびにブラウザが自動でリロードされます。

開発を終了するときはターミナルで `Ctrl + C` を押してください。

---

## フォルダ構成

```
sw-starter/
├── .vscode/
│   ├── extensions.json     ← 推奨拡張機能の設定
│   └── settings.json       ← VS Codeの設定
├── src/
│   ├── _ts/                ← TypeScriptのソースを置く場所
│   ├── _scss/              ← SCSSのソースを置く場所
│   ├── js/                 ← コンパイル後のJS
│   ├── css/                ← コンパイル後のCSS
│   └── index.html          ← HTMLファイル（トップページ）
├── node_modules/           ← パッケージ
├── .markuplintrc           ← Markuplintの設定
├── .prettierignore         ← Prettierの除外設定
├── .prettierrc.json        ← Prettierの設定
├── .stylelintrc.json       ← Stylelintの設定
├── biome.json              ← Biomeの設定
├── bs-config.cjs           ← browser-syncの設定
├── tsconfig.json           ← TypeScriptの設定
└── package.json
```

---

## コマンド一覧

| コマンド              | 内容                               |
| --------------------- | ---------------------------------- |
| `npm run watch`       | 開発環境をすべて起動する           |
| `npm run watch:ts`    | TypeScriptのコンパイル監視のみ起動 |
| `npm run watch:scss`  | SCSSのコンパイル監視のみ起動       |
| `npm run watch:bs`    | ローカルサーバーのみ起動           |
| `npm run lint:script` | TypeScriptのlintを実行             |
| `npm run lint:scss`   | SCSSのlintを実行                   |
| `npm run lint:html`   | HTMLのlintを実行                   |
| `npm run format`      | TS・JS・HTMLをフォーマット         |
| `npm run format:scss` | SCSSをフォーマット                 |

---

## 設定について

フォーマッターおよび診断の設定は、各ツールの推奨設定やデフォルト設定になっています。

プロジェクトに応じてカスタマイズしたい場合は、各公式ドキュメント等を参照してください。

---

## 使用ツール

| ツール                                   | 役割                                   |
| ---------------------------------------- | -------------------------------------- |
| TypeScript                               | 型安全なJavaScriptを書く               |
| Sass                                     | SCSSをCSSにコンパイル                  |
| browser-sync                             | ローカルサーバー・ブラウザ自動リロード |
| npm-run-all                              | 複数コマンドの同時実行                 |
| [Biome](https://biomejs.dev/ja/)         | TS・JS・HTMLのフォーマット＋lint       |
| [Prettier](https://prettier.io/)         | SCSSのフォーマット                     |
| [Stylelint](https://stylelint.io/)       | SCSSのlint                             |
| [Markuplint](https://markuplint.dev/ja/) | HTMLのlint・バリデート                 |

---

## VS Code拡張機能

以下の拡張機能をインストールすると、ファイル保存時に自動でフォーマット・lintが実行されます。

| 拡張機能   | ID                              | 役割                             |
| ---------- | ------------------------------- | -------------------------------- |
| Biome      | `biomejs.biome`                 | TS・JS・HTMLのフォーマット＋lint |
| Prettier   | `esbenp.prettier-vscode`        | SCSSのフォーマット               |
| Stylelint  | `stylelint.vscode-stylelint`    | SCSSのlint                       |
| Markuplint | `yusukehirao.vscode-markuplint` | HTMLのlint・バリデート           |
