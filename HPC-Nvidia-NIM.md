# Nvidia NIMs on HPC
This tutorial explores running Nvidia NIMs on HPC - Nvidia Container Images Models configured with LLM.
### Architecture
NIMs are packaged as container images on a per model/model family basis. Each NIM is its own Docker container with a model, such as meta/llama3-8b-instruct. These containers include a runtime that runs on any NVIDIA GPU with sufficient GPU memory, but some model/GPU combinations are optimized. NIM automatically downloads the model from NGC, leveraging a local filesystem cache if available. Each NIM is built from a common base, so once a NIM has been downloaded, downloading additional NIMs is extremely fast.
### Prerequisites
* NvidiaGPU, x86-64, RHEL8.x, **nvidia-driver:5xx?**, docker
* NVIDIA Container Toolkit 1.14.6 from RegionH Nvidia repo.
* [Nvidia NGC Catalog](https://docs.nvidia.com/ngc/gpu-cloud/ngc-catalog-user-guide/index.html) Firewall allow ip.  **Missing**
* Nvidia NGC Account: Go to [NGC sign-in page](http://ngc.nvidia.com/signin). **Missing**
* glibc>= 2.35 - Current glic=2.30. **Missing**
### Install
[Configure Docker](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html#configuring-docker)
to use the NVIDIA Container Runtime.  
```
nvidia-ctk runtime configure --runtime=docker --config=$HOME/.config/docker/daemon.json
systemctl --user restart docker
systemctl --user restart docker
```
Docker run in Rootless mode.sudo nvidia-ctk config --set nvidia-container-cli.no-cgroups --in-place
```
nvidia-ctk runtime configure --runtime=docker --config=$HOME/.config/docker/daemon.json
systemctl --user restart docker
sudo nvidia-ctk config --set nvidia-container-cli.no-cgroups --in-place
```
### Test Workload
To ensure things are working, run the following command:
```
docker run --rm --runtime=nvidia --gpus all ubuntu nvidia-smi
```
# References
* [Generative AI with NVIDIA NIMs](https://developer.nvidia.com/blog/a-simple-guide-to-deploying-generative-ai-with-nvidia-nim/).
<sub><sub>
[#Mark-Down](https://daringfireball.net/projects/markdown/)
[#Ollama-Releases](https://github.com/ollama/ollama/releases)
