# sixpart-prompt-router
Turns any request into a clean, model-specific 6-part task prompt (ChatGPT or Claude). Prompt-only by default; runs only on explicit “execute”.

## Why
- Deterministic output: single plain fenced block, “Target model” on line 2
- Model-aware routing (ChatGPT or Claude)
- Strict schemas + quality checklist
- Opt-in execution (never auto-run)

## Quick start
- For ChatGPT: `for ChatGPT: <goal> | constraints: <...> | preferred output: <...>`
- For Claude:  `for Claude: <goal> | constraints: <...> | preferred output: <...>`
- Add `execute` to run, and `include code` if you want code in the result.

## License
Apache-2.0 © 2025 Adan T. (@loreada)
