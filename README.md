# agent-optimizer-agent
# Agent Optimizer Agent

A large fraction of current AIS work is optimizing an agentic system for some benchmark by hand. DSPy automates prompt optimization. We should create something similar for agent optimization. Given benchmark and intent, optimize agentic system.

RL already optimizes models and DSPy optimizes agents - this tool would optimize the larger above: agent harnesses and workflow / multi agent system design.

Example:

You are developing an AI scientist system. Currently, a lot of the work there is reading traces, noticing failure modes, then thinking of and testing patches. It seems plausible that current frontier LLMs (Eg Opus 4.5) could automate a substantial part of this. If you have a robust ground truth benchmark (even just the user saying "this output is bad because xyz", that should be enough to optimize an agentic system to do well on it.

NOTE: This could be applied recursively?

**α** = optimizer (given benchmark, optimize agent)
**β** = α
**Loop**: β optimizes α → α becomes new β → repeat

Potential big goodhearting risk, also recursive self improvement generally not good?



## Key questions:

Who are the users
	Devs of agentic systems

How to benchmark agent optimizer performance
	Idea: gather a large set of current benchmarks, test a basic agentic system against them, test an optimized version on them, read the transcripts to make sure there is no goodhearting going on



## Principles

**Human readable**: <10s access to transcripts at all levels (consider Docent-style assistant) - this could help save a lot of compute via fast cheap human validation of correctness. The same applies to auditing agents - transcripts need to be high signal and *very* fast to access.

**Good primitives**: optimizer gets same tools humans use to build agents

 - Tools
 - Workflow organization
 - Prompts

## What exists now?

| System                   | Approach                               | Link                                                         |
| ------------------------ | -------------------------------------- | ------------------------------------------------------------ |
| **DSPy**                 | Declarative + GEPA/MIPROv2             | [github](https://github.com/stanfordnlp/dspy)                |
| **TextGrad**             | Backprop via text feedback             | [github](https://github.com/zou-group/textgrad)              |
| **APE**                  | LLM-generated candidates + selection   | [github](https://github.com/keirp/automatic_prompt_engineer) |
| **Promptomatix**         | DSPy-based, enterprise                 | [github](https://github.com/SalesforceAIResearch/promptomatix) |
| **OpenEvolve**           | OSS AlphaEvolve                        | [github](https://github.com/codelion/openevolve)             |
| **STOP**                 | Seed improver improves itself (1 iter) | [github](https://github.com/microsoft/stop)                  |
| **Darwin Gödel Machine** | Self-rewriting agent via evolution     | [github](https://github.com/jennyzzt/dgm)                    |
| **metaTextGrad**         | Optimizes optimizer prompts            | [arxiv](https://arxiv.org/html/2505.18524v1)                 |
| **AlphaEvolve**          | Evolutionary, production-scale         | [gcloud](https://cloud.google.com/blog/products/ai-machine-learning/alphaevolve-on-google-cloud) |

- [Awesome-LLM-Prompt-Optimization](https://github.com/jxzhangjhu/Awesome-LLM-Prompt-Optimization)
- [LLM-Agent-Optimization-Papers](https://github.com/YoungDubbyDu/LLM-Agent-Optimization)
