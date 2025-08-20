# Usage

## What this project does
Turns any request into a clean, **6-part task prompt** with **model routing** (ChatGPT or Claude). It’s **prompt-only by default** and will **execute only if asked**.

---

## Files in this repo
- `Instructions.txt` — core router/executor behavior (model detection, output shape, execution rules)
- `defaults.json` — overrideable defaults (audience, time horizon, weekly time, timezone, etc.)
- `output_schemas.md` — table / JSON / step-plan formats when the user didn’t specify
- `quality_checklist.md` — final QA gate the output must pass
- `# Claude prompting guide` — Claude-specific guidance (keep this exact filename)

---

## Setup (Custom GPT in ChatGPT)
1. Create a new Custom GPT.
2. In **Knowledge**, upload all repo files **at the root**:
   - `Instructions.txt`
   - `defaults.json`
   - `output_schemas.md`
   - `quality_checklist.md`
   - `# Claude prompting guide` *(exact name; keep as-is)*
3. Save.

> **Tip:** Keep filenames exactly as shown. The Claude guide is discovered by the literal name `# Claude prompting guide`.

---

## How to start a request
Pick a model at the start of your message. If you don’t specify, it defaults to **ChatGPT**.

**ChatGPT example (prompt-only):**
for ChatGPT: design a minimalist login UI in grayscale for desktop
constraints: minimal buttons, clean layout
preferred output: table


**Claude example (prompt-only):**
for Claude: plan a small ASCII text art CLI with three styles
constraints: single file, no external deps
preferred output: step plan


**To execute (opt-in):** add any of these words (**case-insensitive**): `execute`, `run`, `do it`, `apply this`, `perform`.  
**To include code (opt-in):** add `include code` (or say “give me code”).  
**Default:** prompt-only with **no code**.

---

## Output shape you should expect
- One **plain fenced block** (no language tag) containing the **Final 6-part task prompt**  
  - **Line 1:** `Final 6-part task prompt`  
  - **Line 2:** `Target model: ChatGPT` **or** `Target model: Claude`
- If execution was explicitly requested: a separate **“Execution result”** section appears **after** the fence.
- No extra text before/after the fence unless execution is triggered.

---

## Using defaults and overrides
- `defaults.json` values (audience, time horizon, weekly time, timezone, etc.) apply when the user doesn’t provide them.
- To change defaults: edit `defaults.json`, re-upload to the Custom GPT’s Knowledge, and save.

---

## Choosing an output schema
If you didn’t specify a format, the router picks from `output_schemas.md`. You can also ask for a specific one:
- **Table** (lists/options)
- **JSON collection** (structured keys)
- **Step plan** (Goal → Constraints → Steps → Checks → Deliverable)

---

## Quality gate (quick version)
Before accepting an answer, confirm:
- One plain fenced block; first line is **“Final 6-part task prompt”**; second line shows the **target model**
- Dates are `YYYY-MM-DD`; any times include a timezone (e.g., `14:00 America/New_York`)
- 3–7 **Task** bullets, clear **Stop** rules, **assumptions** listed
- Matches the requested schema or a reasonable default schema
- If code was requested, it appears; if not, it doesn’t

> See `quality_checklist.md` for the full list.

---

## Common pitfalls (and fixes)
- **Got code you didn’t want?** Don’t include “include code,” and make sure your ask doesn’t imply code.  
- **Didn’t execute?** Add “execute” or “run” in your message (case-insensitive).  
- **Wrong model?** Start with `for Claude:` or `for ChatGPT:`.  
- **Inconsistent time phrasing?** Use absolute dates and times with timezones in your request.
