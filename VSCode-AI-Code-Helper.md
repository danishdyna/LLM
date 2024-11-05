# AI code helper IBM-granite
## "Continue" - VS Code Extension
* Open VS Code and enter "Extensions"
* Install "Continue" and open (drag extension to right side).
* Quickstart: Select "Local with Ollama".
  - Install Ollama
  - Chat model: ollama pull llama3.1:8b
  - Auto model: ollama pull starcoder2:3b
* Chat: Python code for "main" section.
## "Continue" - Configuration file "config.json"
```
{
  "models": [
    {
      "title": "Granite-code 8B",
      "provider": "ollama",
      "model": "granite-code:8b",
      "apiKey": "EMPTY",
      "apiBase": "http://plnxpersim102.unix.regionh.top.local:11434"
    },
    {
      "title": "Granite-code 20B",
      "provider": "ollama",
      "model": "granite-code:20b",
      "apiKey": "EMPTY",
      "apiBase": "http://plnxpersim102.unix.regionh.top.local:11434"
    },
    {
      "title": "Llama 3.1 8B",
      "provider": "ollama",
      "model": "llama3.1:8b",
      "apiKey": "EMPTY",
      "apiBase": "http://plnxpersim102.unix.regionh.top.local:11434"
    }
  ],
  "tabAutocompleteModel": {
    "title": "Starcoder 3b",
    "provider": "ollama",
    "model": "starcoder2",
    "apiKey": "EMPTY",    
    "apiBase": "http://plnxpersim102.unix.regionh.top.local:11434"
  },
  "customCommands": [
    {
      "name": "test",
      "prompt": "{{{ input }}}\n\nWrite a comprehensive set of unit tests for the selected code. It should setup, run tests that check for correctness including important edge cases, and teardown. Ensure that the tests are complete and sophisticated. Give the tests just as chat output, don't edit any file.",
      "description": "Write unit tests for highlighted code"
    }
  ],
  "contextProviders": [
    {
      "name": "code",
      "params": {}
    },
    {
      "name": "docs",
      "params": {}
    },
    {
      "name": "diff",
      "params": {}
    },
    {
      "name": "terminal",
      "params": {}
    },
    {
      "name": "problems",
      "params": {}
    },
    {
      "name": "folder",
      "params": {}
    },
    {
      "name": "codebase",
      "params": {}
    }
  ],
  "slashCommands": [
    {
      "name": "edit",
      "description": "Edit selected code"
    },
    {
      "name": "comment",
      "description": "Write comments for the selected code"
    },
    {
      "name": "share",
      "description": "Export the current chat session to markdown"
    },
    {
      "name": "cmd",
      "description": "Generate a shell command"
    },
    {
      "name": "commit",
      "description": "Generate a git commit message"
    }
  ],
  "embeddingsProvider": {
    "provider": "ollama",
    "model": "nomic-embed-text"
  }
}
```
