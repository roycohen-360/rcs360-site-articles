# CLAUDE.md

## Working rules (lean)

Always follow these rules to save tokens.

### Reading
- Search before reading: use Grep/Glob to find the exact spot, then read only that range (offset/limit).
- Don't re-read a file you already read or just edited unless it changed.
- Don't dump large outputs. Pipe through `head`, `tail`, `wc -l`, or `grep` first.
- Skip lockfiles, build output, `node_modules`, minified and generated files.

### Tools
- Run independent tool calls in parallel in one message.
- Do small lookups yourself. Spawn a subagent only for broad, independent work you can't do in a handful of calls.
- Prefer one targeted command over several exploratory ones.

### Editing
- Use Edit with a small unique snippet instead of rewriting whole files.
- Change only what the task needs; no drive-by refactors.

### Answers
- Lead with the answer. No preamble, no restating the question, no recap of what you just did.
- Don't paste back code or files the user can already see; reference `path:line`.
- Short lists over long paragraphs. Stop when the question is answered.
- Ask a clarifying question only when you're genuinely blocked; otherwise pick the sensible default and say so in one line.

### Don't
- Don't re-derive facts already established in the conversation.
- Don't list options you won't pursue — give one recommendation.
- Don't poll or loop on status checks; wait for notifications.
