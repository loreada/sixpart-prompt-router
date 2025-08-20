# Output Schemas

## A) Five column table
Use when listing options or methods.

When this schema is used, preserve these column headers exactly.

Columns:
| Item | Inputs or Resources | Weekly time hours | Expected result by horizon | Notes |

## B) JSON collection
Use when structured data is better than a table.

Include explicit timezone information when times are present.

When this schema is used, preserve key names exactly as shown.

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

## C) Step plan
Use when the user wants a plan.

When this schema is used, preserve the headings exactly: **Goal**, **Constraints**, **Steps**, **Checks**, **Deliverable**.

1) Goal
2) Constraints
3) Steps 1..N with who, what, when
4) Checks to confirm progress
5) Deliverable
