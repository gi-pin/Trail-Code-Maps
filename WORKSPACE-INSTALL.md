# Workspace skill installation

Source: https://github.com/gi-pin/Trail-Code-aps
Source commit: b1211efd3eef0efa121b93800e5dd8e547aead77
Skill count: 1

Run from this checkout:

```sh
python3 install-workspace-skills.py /absolute/workspace/path
python3 install-workspace-skills.py /absolute/workspace/path --check
```

Installs relative .agents/skills links without replacing existing entries. Keep this complete checkout under the workspace SKILLS library to retain scripts and assets. Repeat from each workspace checkout. Workspace-local links may not be discovered from a separate nested Git root; explicitly install there if needed.

Discovery: https://learn.chatgpt.com/docs/build-skills . Available on the next turn; restart the session if absent. This installs skill instructions and sources, not CLI dependencies, MCP connections, hooks, credentials, rendering environments or indexes. Verify those prerequisites before running a skill. No external-service end-to-end test was performed.
