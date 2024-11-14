FROM node:23

# 作業ディレクトリ
WORKDIR /app/next-app

RUN npm install -g bun@1.1.34

ENV PATH="/usr/local/bin:$PATH"

# package.jsonが存在する場合のみbun installを実行
RUN if [ -f "package.json" ]; then bun install; else echo "No package.json found, skipping bun install"; fi