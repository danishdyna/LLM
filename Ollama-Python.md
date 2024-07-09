# Ollama Python Library
Tutorial explores using Python 3.8+ in Ollama Python Library API to integrate Ollama LLM Models.
## Python - Install Ollama API
```bash
pip install ollama
```
## Python - Query Ollama LLM Model
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

##

##

<sub><sub>
[#Mark-Down](https://daringfireball.net/projects/markdown)
[#Ollama-Python](https://github.com/ollama/ollama-python)
