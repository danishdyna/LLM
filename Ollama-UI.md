# Ollama User Interface
## Candidates
* [Open WebUI](https://docs.openwebui.com/) (Recommends using docker)
* [SillyTavern](https://sillytavernai.com/)
## Windows Docker
Some how this is not as easy as it seems - WebUI would connet to local Ollama (example worked 28/9-2024).
```
docker run -d -p 3033:8080 --gpus=all -e OLLAMA_HOST="http://host.docker.internal:11434" -v ollama:/root/.ollama -v open-webui:/app/backend/data --add-host=host.docker.internal:host-gateway --name open-webui33 --restart always ghcr.io/open-webui/open-webui:ollama
```
## WebUI Docker - Direct to Ollma host
```
docker run -d -p 3000:8080 -e OLLAMA_HOST=localhost:11434 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
```
## WebUI Docker
```
# OLLAMA_BASE_URL=<Ollama Server URL>
docker run -d -p 3000:8080            --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
docker run -d -p 3000:8080 --gpus all --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:cuda
```
## WebUI Docker - Ollama Support
```
# OLLAMA_BASE_URL=<Ollama Server URL>
docker run -d -p 3000:8080 --gpus=all -v ollama:/root/.ollama -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
```
## URL
http://localhost:3000
