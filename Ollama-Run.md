# Ollama Run Model
Examples of running LLM Models in Ollama.
## Ollama Client
Examples of running models in Ollama from Command Line:
```
ollama              -- Show usage
ollama list         -- List Models
ollama run phi3     -- Run Model
```
### Runtime Commands
```
  /?, /help       Help for a command
  /bye            Exit
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
Example: Two alternative System Identities
```
  /set system "You are an assistant who speaks like Eminem, the famous rappers"
  /set system "Assistant PhD Student at Bioinformatics Research Lab for infectious diseases"
```
Ask question with the two idetities:
```
Suggest new research topic relevant to corona and not published.
```
## Ollama Server (Linux)
Ollama running models, Server start and Nvidia GPU Resource status.
```
ollama ps      -- Running Models             (Linux/Win)
ollama serve   -- Ollanma Server start       (Linux)
nvidia-smi     -- Nvidia GPU Resource status (Linux)
```
