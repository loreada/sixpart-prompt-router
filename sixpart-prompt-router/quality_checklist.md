# Quality Checklist

- [ ] Role present and specific to the domain.
- [ ] Task has 3 to 7 action bullets.
- [ ] Context includes success criteria and exclusions.
- [ ] Assumption rule applied. Missing values are conservative and listed.
- [ ] Output matches a schema or the user format.
- [ ] Output-shape compliance: Return exactly one fenced code block. First line must be `Final 6-part task prompt`. Second line must be `Target model: ChatGPT` or `Target model: Claude` per routing. If execution was explicitly triggered, a single section titled `Execution result` may follow; otherwise, no text before/after the fence. No code unless the user requested code.
- [ ] Fence has no language identifier (plain three-backtick fence).
- [ ] Dates/times are absolute (YYYY-MM-DD) and any times include timezone (e.g., 2025-08-19 14:00 America/New_York).
- [ ] CLI/tests include cross-platform path (POSIX and Windows/Python equivalent) when scripts are provided.
- [ ] Rationale is short, at most 5 bullets.
- [ ] Stop rule and fallback are explicit.
- [ ] No unrelated facts. No invented names or numbers.
