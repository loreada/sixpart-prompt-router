# Output Schemas

> **Datetime convention (applies wherever times appear)**  
> Dates use `YYYY-MM-DD`; datetimes use `YYYY-MM-DD HH:MM America/City` (e.g., `2025-08-19 14:00 America/New_York`).

## A) Five-column table
Use when presenting **ranked options** or short lists with consistent columns.

**Conformance**
- Exactly **5 columns**, header row must match **exactly**:  
  `| Method name | Main resources | Weekly time (hrs) | Estimated progress in 90 days | Summary |`
- Use Markdown vertical bars (`|`) for the header and every row.
- If asked for “**top N**,” return **exactly N rows** (not more, not fewer).

**Minimal example (1 row)**
| Method name | Main resources | Weekly time (hrs) | Estimated progress in 90 days | Summary |
|---|---|---:|---|---|
| Spaced-repetition plan | Anki deck, 30 core papers | 5 | Finish 80% of deck; 3 passes of papers | Tight loop: daily cards + weekly paper notes |

---

## B) JSON collection
Use when structured data beats a table (e.g., multiple items with fields).

**Rules**
- Preserve key names **exactly** as shown. **Do not** add extra keys or reorder.
- Include explicit timezone strings (e.g., `"America/New_York"`) when times exist anywhere in the payload.

**Shape**
```json
{
  "summary": "",
  "items": [
    {
      "name": "",
      "inputs": [],
      "steps": [],
      "estimates": { "time_per_week_hours": 0, "time_horizon": "", "timezone": "" },
      "risks": [],
      "notes": ""
    }
  ],
  "assumptions": [],
  "rationale": [],
  "limits": []
}
