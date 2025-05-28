
念の為、ollamaとopen-webuiを外部ネットワークから隔離した状態で動かす

# モデルのダウンロード
docker compose exec ollama-downloader ollama pull gemma3:4b

# モデルのコピー
docker compose run ollama-sync rsync -av --progress /app/ollama/download/.ollama/ /app/ollama/internal/.ollama/
