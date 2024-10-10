# Stable Diffusion web UI
GitHub: [Stable Diffusion web UI](https://github.com/AUTOMATIC1111/stable-diffusion-webui)  
Wiki: [Features](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features)  
Video: [Install Stable Diffusion - automatic1111](https://youtu.be/kqXpAKVQDNU)  
## 
## webui.sh log
URL Links referenced:
```
https://files.pythonhosted.org/packages/d4/55/90db48d85f7689ec6f81c0db0622d704306c5284850383c090e6c7195a5c/pip-24.2-py3-none-any.whl.metadata
https://pypi.org/simple, https://download.pytorch.org/whl/cu121
https://download.pytorch.org/whl/cu121/torch-2.1.2%2Bcu121-cp311-cp311-linux_x86_64.whl (2200.7 MB)
https://download.pytorch.org/whl/cu121/torchvision-0.16.2%2Bcu121-cp311-cp311-linux_x86_64.whl (6.8 MB)
https://download.pytorch.org/whl/triton-2.1.0-0-cp311-cp311-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (89.2 MB)
https://download.pytorch.org/whl/mpmath-1.3.0-py3-none-any.whl (536 kB)
https://github.com/openai/CLIP/archive/d50d76daa670286dd6cacf3bcd80b5e4823fc8e1.zip --prefer-binary
https://github.com/openai/CLIP/archive/d50d76daa670286dd6cacf3bcd80b5e4823fc8e1.zip
```


Warning:  
Looking in indexes: https://pypi.org/simple, https://download.pytorch.org/whl/cu121   
WARNING: Retrying (Retry(total=4, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProtocolError('Connection aborted.', ConnectionResetError(104, 'Connection reset by peer'))': /whl/cu121/torch/  
Error:  
ERROR: Could not install packages due to an OSError: HTTPSConnectionPool(host='codeload.github.com', port=443): Max retries exceeded with url: /openai/CLIP/zip/d50d76daa670286dd6cacf3bcd80b5e4823fc8e1 (Caused by ProtocolError('Connection aborted.',  
 ConnectionResetError(104, 'Connection reset by peer')))  
```
################################################################
Install script for stable-diffusion + Web UI
Tested on Debian 11 (Bullseye), Fedora 34+ and openSUSE Leap 15.4 or newer.
################################################################

################################################################
Running on hlas0009 user
################################################################

################################################################
Clone stable-diffusion-webui
################################################################
Cloning into 'stable-diffusion-webui'...
remote: Enumerating objects: 34553, done.
remote: Counting objects: 100% (10/10), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 34553 (delta 2), reused 6 (delta 0), pack-reused 34543 (from 1)
Receiving objects: 100% (34553/34553), 35.28 MiB | 27.94 MiB/s, done.
Resolving deltas: 100% (24156/24156), done.
Updating files: 100% (315/315), done.

################################################################
Create and activate python venv
################################################################
Requirement already satisfied: pip in ./venv/lib/python3.11/site-packages (23.2.1)
Collecting pip
  Obtaining dependency information for pip from https://files.pythonhosted.org/packages/d4/55/90db48d85f7689ec6f81c0db0622d704306c5284850383c090e6c7195a5c/pip-24.2-py3-none-any.whl.metadata
  Downloading pip-24.2-py3-none-any.whl.metadata (3.6 kB)
Downloading pip-24.2-py3-none-any.whl (1.8 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.8/1.8 MB 28.8 MB/s eta 0:00:00
Installing collected packages: pip
  Attempting uninstall: pip
    Found existing installation: pip 23.2.1
    Uninstalling pip-23.2.1:
      Successfully uninstalled pip-23.2.1
Successfully installed pip-24.2

################################################################
Launching launch.py...
################################################################
glibc version is 2.28
Check TCMalloc: libtcmalloc_minimal.so.4
libtcmalloc_minimal.so.4 is not linked with libpthread will trigger undefined symbol: pthread_Key_create error
Check TCMalloc: libtcmalloc.so.4
libtcmalloc.so.4 is linked with libpthread,execute LD_PRELOAD=/lib64/libtcmalloc.so.4
Python 3.11.5 (main, Sep 11 2023, 13:54:46) [GCC 11.2.0]
Version: v1.10.1
Commit hash: 82a973c04367123ae98bd9abdf80d9eda9b910e2
Installing torch and torchvision
Looking in indexes: https://pypi.org/simple, https://download.pytorch.org/whl/cu121
WARNING: Retrying (Retry(total=4, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProtocolError('Connection aborted.', ConnectionResetError(104, 'Connection reset by peer'))': /whl/cu121/torch/
Collecting torch==2.1.2
  Downloading https://download.pytorch.org/whl/cu121/torch-2.1.2%2Bcu121-cp311-cp311-linux_x86_64.whl (2200.7 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.2/2.2 GB 20.9 MB/s eta 0:00:00
Collecting torchvision==0.16.2
  Downloading https://download.pytorch.org/whl/cu121/torchvision-0.16.2%2Bcu121-cp311-cp311-linux_x86_64.whl (6.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.8/6.8 MB 31.5 MB/s eta 0:00:00
Collecting filelock (from torch==2.1.2)
  Downloading filelock-3.16.1-py3-none-any.whl.metadata (2.9 kB)
Collecting typing-extensions (from torch==2.1.2)
  Downloading typing_extensions-4.12.2-py3-none-any.whl.metadata (3.0 kB)
Collecting sympy (from torch==2.1.2)
  Downloading sympy-1.13.3-py3-none-any.whl.metadata (12 kB)
Collecting networkx (from torch==2.1.2)
  Downloading networkx-3.3-py3-none-any.whl.metadata (5.1 kB)
Collecting jinja2 (from torch==2.1.2)
  Downloading jinja2-3.1.4-py3-none-any.whl.metadata (2.6 kB)
Collecting fsspec (from torch==2.1.2)
  Downloading fsspec-2024.9.0-py3-none-any.whl.metadata (11 kB)
Collecting triton==2.1.0 (from torch==2.1.2)
  Downloading https://download.pytorch.org/whl/triton-2.1.0-0-cp311-cp311-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (89.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 89.2/89.2 MB 126.8 MB/s eta 0:00:00
Collecting numpy (from torchvision==0.16.2)
  Downloading numpy-2.1.2-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (60 kB)
Collecting requests (from torchvision==0.16.2)
  Downloading requests-2.32.3-py3-none-any.whl.metadata (4.6 kB)
Collecting pillow!=8.3.*,>=5.3.0 (from torchvision==0.16.2)
  Downloading pillow-10.4.0-cp311-cp311-manylinux_2_28_x86_64.whl.metadata (9.2 kB)
Collecting MarkupSafe>=2.0 (from jinja2->torch==2.1.2)
  Downloading MarkupSafe-3.0.1-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (4.0 kB)
Collecting charset-normalizer<4,>=2 (from requests->torchvision==0.16.2)
  Downloading charset_normalizer-3.4.0-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (34 kB)
Collecting idna<4,>=2.5 (from requests->torchvision==0.16.2)
  Downloading idna-3.10-py3-none-any.whl.metadata (10 kB)
Collecting urllib3<3,>=1.21.1 (from requests->torchvision==0.16.2)
  Downloading urllib3-2.2.3-py3-none-any.whl.metadata (6.5 kB)
Collecting certifi>=2017.4.17 (from requests->torchvision==0.16.2)
  Downloading certifi-2024.8.30-py3-none-any.whl.metadata (2.2 kB)
Collecting mpmath<1.4,>=1.1.0 (from sympy->torch==2.1.2)
  Downloading https://download.pytorch.org/whl/mpmath-1.3.0-py3-none-any.whl (536 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 536.2/536.2 kB 43.3 MB/s eta 0:00:00
Downloading pillow-10.4.0-cp311-cp311-manylinux_2_28_x86_64.whl (4.5 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 4.5/4.5 MB 106.8 MB/s eta 0:00:00
Downloading filelock-3.16.1-py3-none-any.whl (16 kB)
Downloading fsspec-2024.9.0-py3-none-any.whl (179 kB)
Downloading jinja2-3.1.4-py3-none-any.whl (133 kB)
Downloading networkx-3.3-py3-none-any.whl (1.7 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.7/1.7 MB 89.1 MB/s eta 0:00:00
Downloading numpy-2.1.2-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (16.3 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 16.3/16.3 MB 123.6 MB/s eta 0:00:00
Downloading requests-2.32.3-py3-none-any.whl (64 kB)
Downloading sympy-1.13.3-py3-none-any.whl (6.2 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.2/6.2 MB 115.5 MB/s eta 0:00:00
Downloading typing_extensions-4.12.2-py3-none-any.whl (37 kB)
Downloading certifi-2024.8.30-py3-none-any.whl (167 kB)
Downloading charset_normalizer-3.4.0-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (142 kB)
Downloading idna-3.10-py3-none-any.whl (70 kB)
Downloading MarkupSafe-3.0.1-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (23 kB)
Downloading urllib3-2.2.3-py3-none-any.whl (126 kB)
Installing collected packages: mpmath, urllib3, typing-extensions, sympy, pillow, numpy, networkx, MarkupSafe, idna, fsspec, filelock, charset-normalizer, certifi, triton, requests, jinja2, torch, torchvision
Successfully installed MarkupSafe-3.0.1 certifi-2024.8.30 charset-normalizer-3.4.0 filelock-3.16.1 fsspec-2024.9.0 idna-3.10 jinja2-3.1.4 mpmath-1.3.0 networkx-3.3 numpy-2.1.2 pillow-10.4.0 requests-2.32.3 sympy-1.13.3 torch-2.1.2+cu121 torchvision-0.16.2+cu121 triton-2.1.0 typing-extensions-4.12.2 urllib3-2.2.3
Installing clip
Traceback (most recent call last):
  File "/chip_work/repo/a1111/stable-diffusion-webui/launch.py", line 48, in <module>
    main()
  File "/chip_work/repo/a1111/stable-diffusion-webui/launch.py", line 39, in main
    prepare_environment()
  File "/chip_work/repo/a1111/stable-diffusion-webui/modules/launch_utils.py", line 394, in prepare_environment
    run_pip(f"install {clip_package}", "clip")
  File "/chip_work/repo/a1111/stable-diffusion-webui/modules/launch_utils.py", line 144, in run_pip
    return run(f'"{python}" -m pip {command} --prefer-binary{index_url_line}', desc=f"Installing {desc}", errdesc=f"Couldn't install {desc}", live=live)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/chip_work/repo/a1111/stable-diffusion-webui/modules/launch_utils.py", line 116, in run
    raise RuntimeError("\n".join(error_bits))
RuntimeError: Couldn't install clip.
Command: "/chip_work/repo/a1111/stable-diffusion-webui/venv/bin/python" -m pip install https://github.com/openai/CLIP/archive/d50d76daa670286dd6cacf3bcd80b5e4823fc8e1.zip --prefer-binary
Error code: 1
stdout: Collecting https://github.com/openai/CLIP/archive/d50d76daa670286dd6cacf3bcd80b5e4823fc8e1.zip

stderr:   WARNING: Retrying (Retry(total=4, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProtocolError('Connection aborted.', ConnectionResetError(104, 'Connection reset by peer'))': /openai/CLIP/zip/d50d76daa670286dd6cacf3bcd80b5e4823fc8e1
  WARNING: Retrying (Retry(total=3, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProtocolError('Connection aborted.', ConnectionResetError(104, 'Connection reset by peer'))': /openai/CLIP/zip/d50d76daa670286dd6cacf3bcd80b5e4823fc8e1
  WARNING: Retrying (Retry(total=2, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProtocolError('Connection aborted.', ConnectionResetError(104, 'Connection reset by peer'))': /openai/CLIP/zip/d50d76daa670286dd6cacf3bcd80b5e4823fc8e1
  WARNING: Retrying (Retry(total=1, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProtocolError('Connection aborted.', ConnectionResetError(104, 'Connection reset by peer'))': /openai/CLIP/zip/d50d76daa670286dd6cacf3bcd80b5e4823fc8e1
  WARNING: Retrying (Retry(total=0, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProtocolError('Connection aborted.', ConnectionResetError(104, 'Connection reset by peer'))': /openai/CLIP/zip/d50d76daa670286dd6cacf3bcd80b5e4823fc8e1
ERROR: Could not install packages due to an OSError: HTTPSConnectionPool(host='codeload.github.com', port=443): Max retries exceeded with url: /openai/CLIP/zip/d50d76daa670286dd6cacf3bcd80b5e4823fc8e1 (Caused by ProtocolError('Connection aborted.', ConnectionResetError(104, 'Connection reset by peer')))


```
