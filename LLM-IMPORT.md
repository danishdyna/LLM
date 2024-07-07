# Import Model in Ollama
## Hugging Face - GGUF Model
Import fine tuned custum Model not found in Ollama.

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
