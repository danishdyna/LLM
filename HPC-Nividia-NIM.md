# Nvidia NIM
This tutorial explores Nvidia NIMs - Nvidia Container Images with configured LLM Model Platform.
### Prerequisites
* NvidiaGPU, x86-64, RHEL8.x,  glibc >= 2.35?, 
* nvidia-driver:5xx?, docker
* NVIDIA Container Toolkit
### Prerequisites: Test
To ensure things are working, run the following command:
```
docker run --rm --runtime=nvidia --gpus all ubuntu nvidia-smi
```
## Ollama Client
Examples of running models in Ollama from Command Line:
```
ollama              -- Show usage
ollama list         -- List Models
ollama run phi3     -- Run Model
```
### Runtime Commands
```
  Ctrl+D, /bye    Exit
```
<sub><sub>
[#Mark-Down](https://daringfireball.net/projects/markdown/)
[#Ollama](https://github.com/ollama)
[#Ollama-Releases](https://github.com/ollama/ollama/releases)
