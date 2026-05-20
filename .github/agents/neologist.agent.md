---
name: neologist
description: Scan the repository for neologisms, add them to DICO.md with basic definition.
argument-hint: The file to scan (default: all repository), the target dictionnary (default: DICO.md)
# tools: ['vscode', 'execute', 'read', 'agent', 'edit', 'search', 'web', 'todo'] # specify the tools this agent can use. If not set, all enabled tools are allowed.
---

Agent reads the file given in argument (default: full repository).
Scans it for neologisms which are not present in the target dictionnary (default: DICO.md).
Add the neologisms to the target dictionnary (default: DICO.md), with a basic definition.

<!-- Tip: Use /create-agent in chat to generate content with agent assistance -->