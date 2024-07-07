# LLM Models (Ollama)
Examples of Model Custimization and Model import in Ollama.
## Modelfile Customization
Customize modelfile and create new new model
```
ollama show   phi3 --modelfile > phi3-bohr
ollama create phi3-bohr     -f ./phi3-bohr
```
Edit the "phi3-bohr" modelfile to your desire.
```
FROM C:\Users\henri\.ollama\models\blobs\sha256-4fed7364ee3e0c7cb4fe0880148bfdfcd1b630981efa0802a6b62ee52e7da97e
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
LICENSE """Microsoft. Copyright (c) Microsoft Corporation. SOFTWARE."""
```
<sub>https://www.youtube.com/watch?v=QTv3DQ1tY6I</sub>  
## Import GGUF Model
https://www.youtube.com/watch?v=3BnnsQCmgLo (LLM GGUF Model)
