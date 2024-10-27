## 目次

- [概要](#概要)
- [技術スタック](#技術スタック)
- [開発準備](#開発準備)
- [環境立ち上げ](#環境立ち上げ)
- [開発モード](#開発モード)
- [アクセス情報](#アクセス情報)
- [ログイン情報](#ログイン情報)
- [備考](#備考)

## 概要

本プロジェクトは、MarkdownでWebサイトを簡単に構築できるサービスをイメージしたプロトタイプです。また、Laravelの学習も兼ねています。  
生成AIの普及によりデザインされたWebサイトの重要性が低下すると考え、デザインを意識せずMarkdownのみで簡単にWebサイトを構築できるサービスのニーズが増してくるだろうと予想しています。このような考えからプロトタイプ作成に至りました。    
また、Markdownの管理にはGit等のバージョン管理システムの概念を導入しています。非エンジニアでも使用できるよう専門的な用語をできるだけ避けたUIにしています。

## 技術スタック

- 言語: PHP
- フレームワーク: Laravel
- JSフレームワーク: Alpine.js
- CSSフレームワーク: Tailwind CSS

## 開発準備

### `.env`ファイルの作成

```sh
cp .env.example .env
```

## 環境立ち上げ

### ビルド

```sh
docker compose build
```

### 起動

```sh
docker compose up -d
```

### マイグレーションの実行

```sh
docker exec -it tremolo-app php artisan migrate
```

### サンプルデータの登録

```sh
docker exec -it tremolo-app php artisan db:seed
```

### 停止

```sh
docker compose down
```

## 開発モード

ローカルで開発する際に、下記のコマンドでVite開発サーバを起動できます。

```sh
docker exec -it tremolo-app npm run dev
```

## アクセス情報

ローカル環境では http://tremolo.localhost でアクセスできます。

## ログイン情報

動作確認のため下記のサンプルユーザを用意しています。`docker exec -it tremolo-app php artisan db:seed`を実行するとサンプルユーザが作成されます。

| メールアドレス | パスワード |
| ---- | ---- |
| bob@example.com | uHrdx55u | 
| john@example.com | uHrdx55u | 

## 備考

- レスポンシブデザインには未対応です
