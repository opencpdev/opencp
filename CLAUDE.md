# CLAUDE.md — rules for every Claude session in this repo

These rules apply to every prompt, every turn, and every command or skill run in this repo.
Hooks in `.claude/settings.json` re-inject this whole file into Claude's context on **every prompt** (UserPromptSubmit) and on every session start, resume, `/clear` and compaction (SessionStart). Do not rely on memory of these rules; use the copy injected with the current prompt.

## Rule 1 — Log every turn to `prompts.md`

- At the end of **every** turn, append the user's prompt and my **full response, verbatim**, to `prompts.md` in the repo root.
- Format:
  ```
  ---
  ## Turn N
  ### Prompt
  <the user's prompt, exactly>
  ### Response
  <my full response, exactly>
  ```
- Never skip a turn. Never rewrite earlier turns. Continue numbering from the last turn in the file.

## Rule 2 — How to respond

For every chat, follow these strictly:

- **Plain English.** Respond in simple, plain English, so it is easy to understand.
- **Precise.** Stick to the topic and context. No unnecessary extra information, unless the user needs to know something, missed something, or is brainstorming an idea.
- **Diagrams.** Use diagrams to make things easy to understand: mermaid (mindmap, flow, flowchart, tree, dependency, etc.) and ASCII diagrams. Only use diagrams that are relevant and meaningful for the topic.

## Rule 3 — Diagram colours

- Background: **dark grey**.
- Diagram components (nodes, boxes): **dark grey, dark orange, or dark brown**.
- Text: **always white**, so it is visible on the dark backgrounds.

Mermaid init block to use:

```
%%{init: {'theme':'base','themeVariables':{'background':'#2b2b2b','primaryColor':'#8a4b08','primaryTextColor':'#ffffff','primaryBorderColor':'#d98a3a','lineColor':'#d98a3a','secondaryColor':'#5c3317','tertiaryColor':'#333333','textColor':'#ffffff','clusterBkg':'#333333','clusterBorder':'#888888','titleColor':'#ffffff','edgeLabelBackground':'#2b2b2b'}}}%%
```

Class colours: `fill:#8a4b08` (dark orange), `fill:#5c3317` (dark brown), `fill:#4a4a4a` (dark grey), always with `color:#ffffff`.
