# ベースイメージ: Node.js 20 (軽量版)
FROM node:20-alpine

# 作業ディレクトリ
WORKDIR /app

# 依存関係ファイルのみコピー (キャッシュ活用)
COPY package*.json ./

# パッケージインストール
RUN npm install

# 全ファイルをコピー
COPY . .

# 開発サーバー起動 (ポート3000)
CMD ["npm", "run", "dev"]
