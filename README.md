## What these notes are

These notes teach how to build AI applications and agents, and how to secure them, one concept at a time. Each note explains what the concept is, walks through an example, shows an attack that worked, and lists the defences.

All examples use an imaginary IT helpdesk with made-up tickets and people, so the domain stays simple and the AI ideas stay in focus.

## How to read them

Read them in number order. Each note builds on the earlier ones. For example, the attacks in RAG (7) and Memory (8) are the same indirect injection first seen in Tool Calling (3), and the fix in Multi-Agent Systems (9) is the rule from The Model Proposes, Code Decides (2).

Progress is tracked in [[0. Syllabus]].

## The notes

| # | Note | Key lesson |
|---|---|---|
| 1 | [[1. Calling a Model]] | Output in the right structure is not the same as correct output |
| 2 | [[2. The Model Proposes, Code Decides]] | Let the model extract facts; let code make the decision |
| 3 | [[3. Tool Calling]] | Authorisation uses the signed-in user, never the model's arguments |
| 4 | [[4. The Agent Loop]] and [[4. The Agent Loop - Exercises]] | The model decides what to do; code decides how far it may go |
| 5 | [[5. Evaluations]] | Measure pass rates; security cases must pass every time |
| 6 | [[6. MCP]] | A tool description written by someone else is an instruction to your model |
| 7 | [[7. RAG]] | Check access before documents reach the model; anyone who writes a document can instruct it |
| 8 | [[8. Memory]] | A saved memory turns untrusted text into trusted instructions for every later session |
| 9 | [[9. Multi-Agent Systems and Code Execution]] | One agent's output is untrusted input to the next; model-written code runs only in a sandbox |
| 10 | [[10. Prompt Injection and Red Teaming]] | Design as if the injection will succeed, then limit what a fooled model can do |
| 11 | [[11. Frameworks]] | A framework's default settings make security decisions for you |
| 12 | [[12. Architecture Review of AI Systems]] | For every text reaching the model, ask who can write it |
| 13 | [[13. Governance]] | Policy, inventory, risk tiers and evidence for every AI system |

## People in the examples

| Name | Role |
|---|---|
| Asha, Ravi, Kiran, Meena | Employees who raise tickets |
| Priya | Helpdesk analyst who uses the AI assistant |
| Mallory | Attacker: an ordinary employee who can write tickets and wiki articles |

## OWASP coverage

The notes cover two OWASP lists: the **Top 10 for LLM Applications 2026** and the **Top 10 for Agentic Applications** (ASI01 to ASI10).

| # | Concept | LLM Top 10 2026 | Agentic Top 10 |
|---|---|---|---|
| 1 | Calling a model | Prompt injection, Misinformation | |
| 2 | The model proposes, code decides | Prompt injection, Excessive agency | ASI01 Agent goal hijack |
| 3 | Tool calling | Excessive agency, Sensitive information disclosure, Improper output handling | ASI02 Tool misuse, ASI03 Identity and privilege abuse |
| 4 | The agent loop | Unbounded consumption, Excessive agency | ASI08 Cascading failures, ASI09 Human-agent trust exploitation |
| 5 | Evaluations | Prompt injection, Misinformation (testing for them) | |
| 6 | MCP | Supply chain, Prompt injection, Sensitive information disclosure | ASI01 Agent goal hijack, ASI04 Agentic supply chain |
| 7 | RAG | Vector and embedding weaknesses, Data and model poisoning, Sensitive information disclosure | ASI06 Memory and context poisoning |
| 8 | Memory | Data and model poisoning | ASI06 Memory and context poisoning |
| 9 | Multi-agent systems and code execution | Excessive agency, Improper output handling | ASI03, ASI05 Unexpected code execution, ASI07 Insecure inter-agent communication, ASI08, ASI10 Rogue agents |
| 10 | Prompt injection and red teaming | Prompt injection | ASI01 Agent goal hijack, ASI09 Human-agent trust exploitation |
| 11 | Frameworks | Supply chain, Sensitive information disclosure, Unbounded consumption | ASI04 Agentic supply chain |
| 12 | Architecture review | All | All |
| 13 | Governance | All | All |

Not yet covered in depth: **Hidden context exposure** (LLM Top 10), which is about attackers reading back instructions or other context the user should not see.
