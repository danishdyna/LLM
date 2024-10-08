# Ollama Model Platform
This tutorial give examples on how to run Open Source LLM Models.  
The Ollama Application Platform is chosen for ease of use and being Open Source.  
Interest is inspired by the AI/GPU revolution starting with GPT-3 in 2020.

**Features**
* Run *On Premesis* - **Security - Sensitive Data**.
* Run on *$1.000 Windows PC* - **General Access**.
* Run from *local application* -- **Python API** 
* Run *Parallel Requests* enables Multiuser Sessions - **ChatBot Service**.
* Run *Parallel Requests* enables Multiuser Code Completion - **IT Team Code Service**.
* Run *Multiple Models* enables RAG with Embeddings and Completion Models - **Query Local Data**.
* Run *Multiple Models* enables "Multiple different Agents" - **Agents - Cool stuff**.

## Ollama Client
Examples of running models in Ollama from Command Line:
```
ollama              -- Show usage
ollama list         -- List Models
ollama run phi3     -- Run Model
```
### Environment
Important environment variables to control Ollama.
```
OLLAMA_HOST=http://127.0.0.1:11434           # Model host and port
#OLLAMA_HOST=127.0.0.1:11434                 # 
OLLAMA_MODELS=/ollama/models                 # Model directory
OLLAMA_NUM_PARALLEL=4                        # Parallel queries - same model
OLLAMA_MAX_LOADED_MODELS=2                   # Parallel models
```
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
ollama ps         -- Running Models             (Linux/Win)
ollama help serve -- Show how to run            (Linux)
ollama serve      -- Ollanma Server start       (Linux)
nvidia-smi        -- Nvidia GPU Resource status (Linux)
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
