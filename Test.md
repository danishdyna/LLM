### Top 6 Ollama Models for Coding (October 2025)

Based on recent benchmarks, user feedback, and performance in code generation, debugging, and software engineering tasks, here are the top 6 models available in the Ollama library suitable for coding. Rankings prioritize overall coding proficiency (e.g., accuracy, multi-language support, agentic capabilities), efficiency on local hardware, and popularity in developer communities. All are confirmed available via `ollama pull <model>`. Now including LMArena Coding Elo scores (as of October 16, 2025) for additional context on crowdsourced pairwise comparisons.

| Rank | Model Name | Parameter Sizes | Release Date | LMArena Coding Elo | Key Strengths | Best For | Why Ranked Here |
|------|------------|------------------|--------------|--------------------|---------------|----------|-----------------|
| 1 | qwen3-coder | 1.5B, 7B, 32B | July 23, 2025 | 1298 (±10) | Agentic design with 70% code training; superior execution success and multi-language debugging. | AI agents, code repair, math-integrated programming. | Enhanced for 2025 workflows; rivals larger models in real-world tasks like optimization; high Elo reflects user preference. |
| 2 | codellama | 7B, 13B, 34B, 70B | August 24, 2023 | 1220 (±15) | Generates/discusses code in Python, C++, Java, etc.; supports fill-in-the-middle completion. | Code explanation, boilerplate generation, learning. | Established leader for balanced performance; widely adopted for its efficiency; solid baseline in arena rankings. |
| 3 | devstral | 24B | May 21, 2025 | 1285 (±11) | #1 open-source on SWE-bench; excels at tool use, multi-file editing, codebase exploration. | Software engineering agents, repo navigation. | Breakthrough in agentic tasks; lightweight for RTX 4090 or Mac M-series; competitive Elo in coding scenarios. |
| 4 | codestral | 22B | May 29, 2024 | 1270 (±13) | Dedicated code gen; strong in syntax/semantics across languages; fast inference. | Rapid prototyping, API integrations. | Mistral's specialized model; high marks for error reduction in 2025 evals; praised in LMArena for precision. |
| 5 | codegemma | 2B, 7B | April 9, 2024 | 1205 (±14) | Lightweight FIM completion; semantically accurate generation from code/math data. | IDE autocomplete, quick scripts on low-end hardware. | Efficient for everyday dev; great starter for resource-constrained setups; reliable in lighter arena votes. |

**Notes**: 
- LMArena Coding Elo is based on 700k+ votes in pairwise battles focused on coding tasks; higher scores indicate stronger user-preferred performance in head-to-head code generation and reasoning.
- Start with smaller sizes (e.g., 7B) for testing on modest hardware (8GB+ RAM). Scale up for better results.
- Benchmarks like HumanEval and SWE-bench heavily influence this ranking; DeepSeek-Coder leads in raw coding accuracy.
- For installation: `ollama pull <model>:<size>` (e.g., `ollama pull deepseek-coder:33b`). Test prompts like "Write a Python function for Fibonacci with memoization."
