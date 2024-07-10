# Ollama Python Library
Tutorial explores using Ollama Python Library in Python 3.8+ to integrate with Ollama LLM Models.
## Install Ollama Library
```bash
pip install ollama
```
## Chat
```python
import ollama
response = ollama.chat(model='phi3', messages=[
  {
    'role': 'user',
    'content': 'Why is the sky blue?',
  },
])
print(response['message']['content'])
```

## Python Create Model - Prompt Engineer SYSTEM Identity
```Python
import ollama
modelfile='''
FROM phi3
SYSTEM You are mario from super mario bros.
'''
ollama.create(model='example', modelfile=modelfile)
```
### Embeddings
```python
ollama.embeddings(model='llama3', prompt='The sky is blue because of rayleigh scattering')
```
<sub><sub>
[#Mark-Down](https://daringfireball.net/projects/markdown)
[#Ollama-Python](https://github.com/ollama/ollama-python)
[#Ollama-API](https://github.com/ollama/ollama/blob/main/docs/api.md)
