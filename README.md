# thoughts-recorder

This is a tool to export Claude Code conversations so that you can easily review them later. I've found this very useful in the process of creating new Skills.

Based on [this gist](https://gist.github.com/Kabilan108/7b0912cee5c89efb43ed2e0dcf6ac8e0) by @Kabilan108 🙌

Features I added with Claude Code:
- [x] Export an arbitrary trace previously exported to a jasonlines file (as `/export` does).
- [x] Fix nested fences inside thinking blocks.
- [x] Turn-based format. We group assistant responses so first level items are the actual user instructions and the model responses. Previously, tool calls and agentic actions appeared inside "User" turns and it was harder to follow the conversation.

## How to Use

```
uv run https://raw.githubusercontent.com/pcuenca/thoughts-recorder/refs/heads/main/utils/export-cc-trace.py --help
```

To Do
- [x] ~~Package as a Skill~~. On second thought, `uv run` is fine. Not everything needs to be a Skill.
