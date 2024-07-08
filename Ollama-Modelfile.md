# Ollama Modelfile
Examples of Model Custimization and Model import in Ollama.
## Modelfile - Model Customization
Customize modelfile and create new new model
```
ollama show   phi3     --modelfile > phi3-phd    -- Show Modelfile
notepad       phi3-phd                           -- Edit Modelfile
```
Edit the "phi3-phd" modelfile to your desire.
```
# Modelfile "phi3-phd"
FROM phi3:latest
TEMPLATE "{{ if .System }}<|system|>
{{ .System }}<|end|>
{{ end }}{{ if .Prompt }}<|user|>
{{ .Prompt }}<|end|>
{{ end }}<|assistant|>
{{ .Response }}<|end|>
"
PARAMETER temperature 1      -- 1=Creative, 0.8=Default, 0.6=Coherent
PARAMETER stop <|user|>
PARAMETER stop <|assistant|>
PARAMETER stop <|system|>
PARAMETER stop <|end|>
PARAMETER stop <|endoftext|>
PARAMETER num_keep 4
SYSTEM "You are an assistant PhP Student at Bioinformatics Research Lab for infectious diseases."
```
Create new model, list model and run model with query: [Responce-Pipeline](https://github.com/danishdyna/LLM/blob/main/Responce-Pipeline.md)
```
ollama create phi3-phd     -f ./phi3-phd         -- Make New Model
ollama list   phi3                               -- List New Model
ollama run    phi3-phd                           -- Run  New Model
Suggest resourch topic using machine learning and outline pipe-line in Python pseudocode examples.
```
<sub><sub>
[#Ollama](https://github.com/ollama/ollama)
[#Ollama-Modelfile](https://github.com/ollama/ollama/blob/main/docs/modelfile.md)
[#Customize-Model](https://www.youtube.com/watch?v=QTv3DQ1tY6I)</sub></sub> 
