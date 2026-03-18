# thoughts-recorder

Export Claude Code conversations to nice Markdown that you can easily read later.

I've found this very useful in the process of creating new Skills.

Based on [this gist](https://gist.github.com/Kabilan108/7b0912cee5c89efb43ed2e0dcf6ac8e0) by @Kabilan108 🙌

Features I added with Claude Code:
- [x] Export an arbitrary trace previously exported to a jasonlines file (as `/export` does).
- [x] Fix nested fences inside thinking blocks.
- [x] Turn-based format. We group assistant responses so first level items are the actual user instructions and the model responses. Previously, tool calls and agentic actions appeared inside "User" turns and it was harder to follow the conversation.

## How to Use

Just `uv run` it from GitHub:
```bash
uv run https://raw.githubusercontent.com/pcuenca/thoughts-recorder/refs/heads/main/utils/export-cc-trace.py --help
```

Help output:
```
usage: export-cc-traceToKQT9.py [-h] [--file FILE_PATH] [--session SESSION_ID] [--latest N] [--output-dir OUTPUT_DIR]
                                [--format {md,xml,all}] [--export-name EXPORT_NAME] [--anonymize]

Export Claude Code sessions to structured directories

options:
  -h, --help            show this help message and exit
  --file FILE_PATH      Export from an arbitrary JSONL trace file (bypasses ~/.claude lookup)
  --session SESSION_ID  Export a specific session ID (supports prefix match)
  --latest N            Export only the N most recent sessions
  --output-dir OUTPUT_DIR
                        Custom output directory (default: .claude-sessions/ in project root)
  --format {md,xml,all}
                        Output format (default: md)
  --export-name EXPORT_NAME
                        Custom name for the export directory (only with --session)
  --anonymize           Exclude user/machine info from export
```

To Do
- [x] ~~Package as a Skill~~. On second thought, `uv run` is fine. Not everything has to be a Skill.
