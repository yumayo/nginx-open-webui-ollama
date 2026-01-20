
念の為、ollamaとopen-webuiを外部ネットワークから隔離した状態で動かす

# 起動
docker compose up -d


# モデルのダウンロード
docker compose exec ollama-downloader ollama pull gemma3:4b

# モデルのコピー
docker compose run ollama-sync rsync -av --progress /app/ollama/download/.ollama/ /app/ollama/internal/.ollama/

# ヘルプ

## ollamaのコンテナ自体を更新したい

```sh
docker rmi ollama/ollama:latest
```

## コンテキストサイズを調整する

https://docs.ollama.com/context-length

```sh
OLLAMA_CONTEXT_LENGTH=256000
```
