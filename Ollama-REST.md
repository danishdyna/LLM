# Ollama REST API
Tutorial on [Ollama REST API](https://github.com/ollama/ollama/blob/main/docs/api.md) is a HTTP based protocol between Ollama Client and Server.

## POST Request - Generate Completion Responce
Request with Prompt and Generate Responce with given Model.
```
POST /api/generate
```
### POST Request - Responce in JSON
Request with Prompt for Responce in JSON with given Model and no streaming ("stream": false).
```
curl http://localhost:11434/api/generate -d '{
  "model": "phi3.5",
  "prompt": "What color is the sky at different times of the day? Respond using JSON",
  "format": "json",
  "stream": false
}'
```
Responce as a single JSON object including statistics.
```
curl http://localhost:11434/api/generate -d '{
  "model": "phi3.5",
  "created_at": "2023-11-09T21:07:55.186497Z",
  "response": "{\n\"morning\": {\n\"color\": \"blue\"\n},\n\"noon\": {\n\"color\": \"blue-gray\"\n},\n\"afternoon\": {\n\"color\": \"warm gray\"\n},\n\"evening\": {\n\"color\": \"orange\"\n}\n}\n",
  "done": true,
  "context": [1, 2, 3],
  "total_duration": 4648158584,
  "load_duration": 4071084,
  "prompt_eval_count": 36,
  "prompt_eval_duration": 439038000,
  "eval_count": 180,
  "eval_duration": 4196918000
}'
```
<sub><sub>
[#Mark-Down](https://daringfireball.net/projects/markdown/)
[#Ollama](https://github.com/ollama)
[#Ollama REST API](https://github.com/ollama/ollama/blob/main/docs/api.md)
[#Ollama Python API](https://github.com/ollama/ollama-python)
[#REST API](https://www.ibm.com/topics/rest-apis)
