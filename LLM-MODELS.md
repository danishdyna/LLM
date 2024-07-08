# LLM Models (Ollama)
Examples of Model Custimization and Model import in Ollama.
## Modelfile - Model Customization
Customize modelfile and create new new model
```
ollama show   phi3 --modelfile > phi3-eminem        -- Show Modelfile
notepad       phi3-eminem                           -- Edit Modelfile
ollama create phi3-eminem     -f ./phi3-eminem      -- Make New Model

ollama list   phi3                                  -- List New Model
ollama run    phi3-eminem                           -- Run  New Model
```
Edit the "phi3-eminem" modelfile to your desire.
```
# Modelfile "phi3-eminem"
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
SYSTEM "You are an assistant who speaks like Eminem, the famous rapper."
```
<sub><sub>
[#Ollama](https://github.com/ollama/ollama)
[#Ollama-Modelfile](https://github.com/ollama/ollama/blob/main/docs/modelfile.md)
[#Customize-Model](https://www.youtube.com/watch?v=QTv3DQ1tY6I)</sub></sub> 
