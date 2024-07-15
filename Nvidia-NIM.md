# Nvidia NIM
This tutorial explores running Nvidia NIM - Nvidia Container Images Models configured with LLM.
### Architecture
NIMs are packaged as container images on a per model/model family basis. Each NIM is its own Docker container with a model, such as meta/llama3-8b-instruct. These containers include a runtime that runs on any NVIDIA GPU with sufficient GPU memory, but some model/GPU combinations are optimized. NIM automatically downloads the model from NGC, leveraging a local filesystem cache if available. Each NIM is built from a common base, so once a NIM has been downloaded, downloading additional NIMs is extremely fast.
### License
Open Source License - Apache 2.0.

## NGC - Nvidia GPU Cloud
NVIDIA NGC™ is the portal of enterprise services, software, management tools, and support for end-to-end AI and digital twin workflows.  
[NGC Catalog - NIM Microcervices](https://catalog.ngc.nvidia.com/)  
### NGC - Login
Login or create Nvidia User Account: [NGC Login](https://ngc.nvidia.com/signin) Shop2024
Get familier with NGC: [NGC Catalog User Guide](https://docs.nvidia.com/ngc/gpu-cloud/ngc-catalog-user-guide/index.html)
### NGC - API Key
https://org.ngc.nvidia.com/setup/api-key - Generate and save API-Key.
```
docker login nvcr.io
Username: $oauthtoken
Password: <API-KEY>
```
## NIM OnPrem
### Prerequisites
* NvidiaGPU, x86-64, RHEL8.x, **nvidia-driver:5xx?**, docker
* NVIDIA Container Toolkit 1.14.6 from RegionH Nvidia repo.
* HTTPS Access, GitHub: github.io(185.199.110.153, 185.199.111.153, 185.199.108.153,185.199.109.153). **??**
* HTTPS Access, [Nvidia NGC Catalog](https://docs.nvidia.com/ngc/gpu-cloud/ngc-catalog-user-guide/index.html): nvcr.io(44.232.51.65, 54.191.152.110)   **Missing**
* Nvidia NGC Account: Go to [NGC sign-in page](http://ngc.nvidia.com/signin). **Missing**
* glibc>= 2.35 (current glic 2.30). **Missing**
### Docker on Win11
Configure Windows Subsystem for Linux WSL in PowerShell (turn on Windows Feature).
``` PowerShell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
wsl --install -d Ubuntu                         # Takes 20 min.
wsl --set-default-version 2
```
Download Linux kernel update: [Error: 0x800701bc WSL 2.](https://learn.microsoft.com/en-us/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package)  
``` PowerShell
wget https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
wsl_update_x64.msi      # 
```

Hint: Installing "Docker Desktop" WSL first can resulted in boot freeze.  
Force reboot, disrupt boot - repair!
### Docker on RHEL8
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
## References
* [Generative AI with NVIDIA NIMs](https://developer.nvidia.com/blog/a-simple-guide-to-deploying-generative-ai-with-nvidia-nim/).

<sub><sub>
[#Mark-Down](https://daringfireball.net/projects/markdown/)
[#Ollama-Releases](https://github.com/ollama/ollama/releases)
