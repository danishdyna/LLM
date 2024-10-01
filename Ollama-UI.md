# Ollama User Interface
## Candidates
* [Open WebUI](https://docs.openwebui.com/) (Docker)
* [SillyTavern](https://sillytavernai.com/)
## WebUI on Linux
Running on WebUI Linux may pose problems connecting to the Ollama Backend. 
### Docker container
The WebUI documentation suggest the command for running the docker image list below. 
```
docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_MODELS="/chip_work/repo/ollama/models" -e OLLAMA_BASE_URL="http://127.0.0.1:11434" --name open-webui --restart always danishdyna/webui:ollama
docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```
### Web app
The WebUI documentation suggest calling WebUI on port 8080.
```
http://localhost:8080
```
Check the Ollama Backend connection in the menu: http://localhost:8080/admin/settings, Connections, "Verify connection".
### WebUI snake test
Run WebUI from the borwser select model "mixtral:instruct" and ask: ```Python code for snake game.```  
Run VS Code and prepare a virtual python environment.
* Download and install [Python](https://www.python.org/downloads/) (Add Python to PATH).
* Create Python virtual environment:  
```
python -m venv snake
snake\Scripts\activate
pip install pygame
```
Edit the filesnake.py with the result from WebUI and run.
## WebUI on Windows
WebUI on Windows Docker with local Ollama backend. Some how this is not as easy as it seems - WebUI would connet to local Ollama (example worked 28/9-2024).  
Note, settings are persistent and will survive from previous runs in the Docker volumes.
```
docker run -d -p 3033:8080 --gpus=all -e OLLAMA_HOST="http://host.docker.internal:11434" -v ollama:/root/.ollama -v open-webui:/app/backend/data --add-host=host.docker.internal:host-gateway --name open-webui33 --restart always ghcr.io/open-webui/open-webui:ollama
```
## OLD WebUI Docker - Direct to Ollma host
```
docker run -d -p 3000:8080 -e OLLAMA_HOST=localhost:11434 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
```
## OLD WebUI Docker
```
# OLLAMA_BASE_URL=<Ollama Server URL>
docker run -d -p 3000:8080            --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
docker run -d -p 3000:8080 --gpus all --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:cuda
```
## OLD WebUI Docker - Ollama Support
```
# OLLAMA_BASE_URL=<Ollama Server URL>
docker run -d -p 3000:8080 --gpus=all -v ollama:/root/.ollama -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
```
## URL
http://localhost:3000
