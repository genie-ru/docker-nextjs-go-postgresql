# docker-go-nextjs

Docker Composeを用いて、Next.jsとGo (Echo × Air) での開発環境を構築するテンプレートです。

## インストール方法

### 1. リポジトリをクローンする

まず、このテンプレートリポジトリをクローンします。

```bash
git clone 
```

### 2. 開発環境を構築する

クローンしたディレクトリに移動し、Docker Composeで開発環境を立ち上げます。

```bash
cd docker-go-nextjs
docker compose up -d --build
```

### 3. ブラウザで各サービスを確認する

以下のURLから、各サービスが正常に起動しているか確認できます：

- [Next.js (Frontend)](http://localhost:3000/)
- [Storybook (UIコンポーネント)](http://localhost:6006/)
- [Backend (Go API)](http://localhost:1323/)

## 背景

Dockerを使用して、Next.jsとGoで開発を行うことが多いため、効率的に開発環境をセットアップできるテンプレートを作成しました。

## 開発環境の初期セットアップ

このプロジェクトでは、以下のコマンドを使用してNext.jsアプリの作成やStorybookの初期化を行います。

```bash
# Next.jsアプリをTypeScriptで作成
docker compose run --rm front bunx create-next-app@latest . --ts

# Storybookの初期化
docker compose run --rm front npx storybook init

# Storybook for Next.jsをインストール
docker compose run --rm front npm install --save-dev @storybook/nextjs

# Storybookの設定ファイル（package.jsonなど）に追記
"storybook": "storybook dev -p 6006 --ci",

# shadcn/UIのインストール
docker compose run --rm front bunx --bun shadcn@latest init

docker compose run --rm front bun add @react-three/fiber @react-three/drei

docker compose run --rm front bun add zod


```

## 開発環境のクリーンアップ

不要なコンテナや一時的なコンテナを削除するには、以下のコマンドを使用してください：

```bash
docker compose down --remove-orphans
```

このコマンドで一時コンテナや停止中のコンテナが削除され、クリーンな状態で開発を再開できます。

---

### 補足

このREADMEには、実行するコマンドの説明とURLの確認項目を加えています。
