# Ollama Import Model (GGUF) 
## [Hugging Face Models](https://huggingface.co/models)
Import fine tuned custom GGUF Models not found in [ollama.com/libraries](https://ollama.com/library).

### [Jackalope 7B](https://huggingface.co/openaccess-ai-collective/jackalope-7b)
Jackalope is fintuned on SlimOrca dataset, PIPPA, etc. on Mistral 7B.
SlimOrca efficiently trains models for Multi-Turn Conversation.

### Quantized Models
Select the GGUF Quantized version (what Ollama runs) in models main tree on HugginFace.  
https://huggingface.co/TheBloke/jackalope-7B-GGUF/tree/main



<sub>[#Import-GGUF-Model](https://www.youtube.com/watch?v=3BnnsQCmgLo)

Customize modelfile and create new new model
```
ollama show   phi3 --modelfile > phi3-bohr
ollama create phi3-bohr     -f ./phi3-bohr
ollama run    phi3-bohr
```
Edit the "phi3-bohr" modelfile to your desire.
```
FROM phi3
TEMPLATE "{{ if .System }}<|system|>
{{ .System }}<|end|>
{{ end }}{{ if .Prompt }}<|user|>
{{ .Prompt }}<|end|>
{{ end }}<|assistant|>
{{ .Response }}<|end|>
"
PARAMETER stop <|user|>
PARAMETER stop <|assistant|>
PARAMETER stop <|system|>
PARAMETER stop <|end|>
PARAMETER stop <|endoftext|>
PARAMETER num_keep 4
LICENSE """Copyright (c) Microsoft Corporation."""
```
