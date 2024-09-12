# Compute - Hardware Platform
This tutorial gives examples on how to run LLM Models on On-Prem Hardware Platforms.    
The $1K Windows PC gives easy general access to On-Prem LLMs with a limited resource frame.  
The $300 Linux GPU Cluster gives a state of the art powerful On-Prem access to LLMs. 
  
## Ollama for Windows
Download and install from [ollama.com](https://ollama.com/download)

### Runtime Commands
```
  /?, /help       Help for a command
  /set            Set session variables
  /show           Show model information
  /load <model>   Load a session or model
  /save <model>   Save your current session
  /clear          Clear session context
  /? shortcuts    Help for keyboard shortcuts
```
### Runtime Set Behavior:
```
  /set parameter ...     Set a parameter
  /set system <string>   Set system message
  /set template <string> Set prompt template
  /set history           Enable history
  /set nohistory         Disable history
  /set wordwrap          Enable wordwrap
  /set nowordwrap        Disable wordwrap
  /set format json       Enable JSON mode
  /set noformat          Disable formatting
  /set verbose           Show LLM stats
  /set quiet             Disable LLM stats
```
### System Identity
Ask question with different *System Idetity*: [Responce-Grant](https://github.com/danishdyna/LLM/blob/main/Responce-Grant.md).
```
/set system "You are an assistant Responcible for grant applications at Research Lab for infectious disease"
Suggest new research topic relevant to corona and not published.
```
```
/set system "Assistant PhD Student at Bioinformatics Research Lab for infectious diseases"
Suggest new research topic relevant to corona and not published.
```
```
/set system "Assistant who speaks like Eminem, the famous rappers know for Slim Shady alter ego"
Rap over social injustice inflicted on a less forunate character. 
```
## Ollama Monitoring
Ollama running models, Server start and Nvidia GPU Resource status.
```
ollama ps      -- Running Models             (Linux/Win)
ollama serve   -- Ollanma Server start       (Linux)
nvidia-smi     -- Nvidia GPU Resource status (Linux)
```
## Ollama HTTP Server
Ollama HTTP Server listens on port 11434 and will default output status.
```
$ curl http://127.0.0.1:11434

StatusCode        : 200
StatusDescription : OK
Content           : Ollama is running
RawContent        : HTTP/1.1 200 OK
                    Content-Length: 17
                    Content-Type: text/plain; charset=utf-8
                    Date: Tue, 09 Jul 2024 15:21:35 GMT

                    Ollama is running
```
<sub><sub>
[#Mark-Down](https://daringfireball.net/projects/markdown/)
[#Ollama](https://github.com/ollama)
[#Ollama-Releases](https://github.com/ollama/ollama/releases)
