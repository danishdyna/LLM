# Compute - Hardware Platform
This tutorial gives examples on how to run LLM Models on On-Prem Hardware Platforms.    
The $1K Windows PC gives easy general access to On-Prem LLMs with a limited resource frame.  
The $300 Linux GPU Cluster gives a state of the art powerful On-Prem access to LLMs. 
  
## Ollama on Windows PC
### Installtion on Windows
Download and install from
https://ollama.com/download  
Run Ollama from Command Console or PowerShell 
```
ollama list
ollama run phi
```
### Monitor on Windows
Monitor Ollama memory usage on Windows - alternatively use **MS Task Monitor**.
```
tasklist | findstr /i "ollama"
```
