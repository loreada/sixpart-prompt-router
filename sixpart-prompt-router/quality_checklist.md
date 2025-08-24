# Quality Checklist

- [ ] **Role** present and specific to the domain.  
- [ ] **Task** has **3–7** action bullets.  
- [ ] **Context** includes success criteria and exclusions.  
- [ ] **Assumption rule** applied: if inputs are missing, use **`defaults.json`** (audience, time horizon, timezone) and list assumptions explicitly.  
- [ ] **Output schema** matches the user’s specified format or one of the allowed schemas in **`output_schemas.md`**:  
      **A) Five-column table**, **B) JSON collection** (strict keys, no extras), **C) Step plan** (fixed headings).  
- [ ] **Output-shape compliance (hard gate):**  
      Return **exactly one** fenced code block (plain; **no language tag**).  
      **Line 1:** `Final 6-part task prompt` • **Line 2:** `Target model: ChatGPT` or `Target model: Claude` (per routing).  
      If execution was explicitly triggered, a single **`Execution result`** section may follow; otherwise **no text** before/after the fence.  
      No code unless the user requested code.  
- [ ] **If code was requested:** it appears **only after** the main fence in a section titled **`Code`**, inside a language-tagged code fence (e.g., a Python code fence).  
- [ ] **Dates/times are absolute and canonicalized:**  
      Dates `YYYY-MM-DD`; datetimes `YYYY-MM-DD HH:MM America/City` (e.g., `2025-08-19 14:00 America/New_York`).  
- [ ] **Rationale** is short: ≤ **5 bullets**.  
- [ ] **Stop rule** and **fallback** are explicit.  
- [ ] **No unrelated facts.** **No invented** names or numbers.  

---

### Compliance Tests (self-check before emitting)

- Exactly **one** fenced code block; **no language tag**.  
- First two lines match spec **exactly**.  
- Nothing outside the fence unless **`Execution result`** applies; if present, it appears **after** the fence.  
- If code was requested, it appears only in **`Code`** (language-tagged code fence) **after** the main fence.  
- Output matches an **allowed schema** or the user’s requested format.  
- Date/time strings conform to the canonical formats above.  
- Rationale ≤ **5 bullets**.  
- Stop rule & fallback present.
