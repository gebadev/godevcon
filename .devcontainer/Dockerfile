FROM ubuntu:24.04

# 必要なツールのインストール
RUN apt-get update && apt-get install -y \
    wget \
    git \
    build-essential \
    curl \
    ca-certificates \
    gnupg \
    && rm -rf /var/lib/apt/lists/*

# Go 1.24.1のダウンロードとインストール
RUN wget https://golang.org/dl/go1.24.1.linux-amd64.tar.gz \
    && tar -C /usr/local -xzf go1.24.1.linux-amd64.tar.gz \
    && rm go1.24.1.linux-amd64.tar.gz

# 環境変数の設定
ENV PATH="/usr/local/go/bin:${PATH}"
ENV GOPATH="/workspace/go"
ENV PATH="${GOPATH}/bin:${PATH}"

# 作業ディレクトリの設定
WORKDIR /workspace

# Go言語の初期設定
RUN go version
RUN mkdir -p "${GOPATH}/src" "${GOPATH}/bin" "${GOPATH}/pkg"