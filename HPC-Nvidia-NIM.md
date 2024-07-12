# Nvidia NIM
This tutorial explores Nvidia NIMs - Nvidia Container Images with configured LLM Model Platform.
### Prerequisites ()
* NvidiaGPU, x86-64, RHEL8.x,  glibc >= 2.35?, 
* nvidia-driver:5xx?, docker
* glibc >= 2.35?,
* NVIDIA Container Toolkit - Repo Root: Missing in RegionH Subscription  
https://nvidia.github.io/libnvidia-container/stable/rpm/
### Prerequisites: Test
To ensure things are working, run the following command:
```
docker run --rm --runtime=nvidia --gpus all ubuntu nvidia-smi
```
### Architecture
NIMs are packaged as container images on a per model/model family basis. Each NIM is its own Docker container with a model, such as meta/llama3-8b-instruct. These containers include a runtime that runs on any NVIDIA GPU with sufficient GPU memory, but some model/GPU combinations are optimized. NIM automatically downloads the model from NGC, leveraging a local filesystem cache if available. Each NIM is built from a common base, so once a NIM has been downloaded, downloading additional NIMs is extremely fast.

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
