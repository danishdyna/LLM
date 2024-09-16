# Compute - Hardware Platform
This tutorial gives Ollama examples on how to run LLM Models on On-Prem Hardware Platforms.    
The $1K Windows PC gives easy general access to On-Prem LLMs with a limited resource frame.  
The $300 Linux GPU Cluster gives a state of the art powerful On-Prem access to LLMs. 
  
## Ollama on Windows PC
Windows PCs laking GPU/TPU (AI Accceletators) have compute and memory constraints.
### Models on Windows
Choose models with a memory footprint that matches available system memory and your impations.  
Model relases are frequent and recommendations likely outdated - well heres my take:

* [phi3.5](https://techcommunity.microsoft.com/t5/ai-azure-ai-services-blog/discover-the-new-multi-lingual-high-quality-phi-3-5-slms/ba-p/4225280) (3.8b Parameters, 2.2GB Size, 128K Tokens, April 2024 Release) - Favorite.

For exploring embeddings at a later time - I have mu eyes on _all-minilm_ (22m Parameters, 46MB Size, Embeddings model, Maj 2024 Release). Embeddings only!

### Installation and run on Windows
Download and install from
https://ollama.com/download  
The Ollame Backgound Service is started when Ollama is run from Command Console or PowerShell.
```
ollama list
ollama run phi
```
### Monitor on Windows
Monitor Ollama memory usage on Windows - alternatively use MS Task Monitor.
```
tasklist | findstr /i "ollama"
```
## Ollama on RHEL Linux with Nividia GPU
The scope is Limux RHEL Server with AMD 64 Core CPu, 1TB RAM and Nividia A100/40GB GPUs.
### Models on Windows
Within the scope most Open Source LLM may run, 
Model relases are frequent and recommendations likely outdated - well heres my take:

*  
### Installation and run on Linux
Download and install from
https://ollama.com/download  
The Ollame Backgound Service must be started explicily for the Ollama Client to run from bash shell command line.
```
$ module load ollama
$ ollama serve
2024/09/16 09:31:14 routes.go:1109: INFO server config env="map[CUDA_VISIBLE_DEVICES: GPU_DEVICE_ORDINAL: HIP_VISIBLE_DEVICES: HSA_OVERRIDE_GFX_VERSION: OLLAMA_DEBUG:false OLLAMA_FLASH_ATTENTION:false OLLAMA_HOST:http://127.0.0.1:11434 OLLAMA_INTEL_GPU:false OLLAMA_KEEP_ALIVE:5m0s OLLAMA_LLM_LIBRARY: OLLAMA_MAX_LOADED_MODELS:2 OLLAMA_MAX_QUEUE:512 OLLAMA_MODELS:/chip_work/repo/ollama/models OLLAMA_NOHISTORY:false OLLAMA_NOPRUNE:false OLLAMA_NUM_PARALLEL:4 OLLAMA_ORIGINS:[http://localhost https://localhost http://localhost:* https://localhost:* http://127.0.0.1 https://127.0.0.1 http://127.0.0.1:* https://127.0.0.1:* http://0.0.0.0 https://0.0.0.0 http://0.0.0.0:* https://0.0.0.0:* app://* file://* tauri://*] OLLAMA_RUNNERS_DIR: OLLAMA_SCHED_SPREAD:false OLLAMA_TMPDIR: ROCR_VISIBLE_DEVICES:]"

```
In a new shell run the Ollama Client
```
ollama list
ollama run phi
```
### Monitor on Windows
Monitor Ollama memory usage on Windows - alternatively use MS Task Monitor.
```
tasklist | findstr /i "ollama"
```
