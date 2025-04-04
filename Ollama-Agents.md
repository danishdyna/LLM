# Ollama Agents
## Web Search Agent
Create a simple AI Agent to search web with frameworks like LangGraph or AutoGen.
Install the required Python packages:

    pip install langgraph langchain_community tiktoken langchainhub chromadb langchain tavily-python langchain-openai
Create a Python script to define and run your AI agent:
```python
from langchain_community.tools.tavily_search import TavilySearchResults
from langgraph.prebuilt import create_react_agent
from langchain_openai import ChatOpenAI

# Initialize the language model
llm = ChatOpenAI(model="mistral", api_key="ollama", base_url="http://localhost:11434/v1")

# Define the tools the agent can use
tools = [TavilySearchResults(max_results=3)]
llm_with_tools = llm.bind_tools(tools)

# Create the agent executor
agent_executor = create_react_agent(llm_with_tools, tools)

# Run the agent with a sample input
response = agent_executor.invoke({"messages": [("user", "Explain artificial intelligence")]})


for message in response['messages']:
    print(message.content)
```
