FROM golang:1.23-alpine

WORKDIR /app

# 必要なツール（Gitなど）をインストール
RUN apk update && apk add --no-cache git

# Air（ホットリロードツール）をインストール
RUN go install github.com/air-verse/air@v1.61.1

# 依存関係ファイルのコピー
COPY go.mod ./
# COPY go.sum ./  # まだ無いのでコメントアウト

# 依存関係のダウンロード
RUN go mod download

# Airを使ってサーバー起動
CMD ["air", "-c", ".air.toml"]
