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
* all-minilm (22m Parameters, 46MB Size, Embeddings model, Maj 2024 Release) - Not used.

### Installation on Windows
Download and install from
https://ollama.com/download  
Run Ollama from Command Console or PowerShell 
```
ollama list
ollama run phi
```
### Monitor on Windows
Monitor Ollama memory usage on Windows - alternatively use MS Task Monitor.
```
tasklist | findstr /i "ollama"
```
