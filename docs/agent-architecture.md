# Agent Architecture

LoganiteAI is intentionally minimal.

The architecture favors clarity over complexity.

---

## Components

agent/
  run.py          # main execution loop
  observe.py      # environment observation
  decide.py       # reflection and evaluation
  memory.json     # persistent memory store
  recommend.md    # human‑readable output
---

## Execution Flow
1. `run.py` loads persistent memory
2. `observe.py` generates a new observation
3. `decide.py` reflects on the observation
4. Results are written to:
   - `memory.json` (long‑term record)
   - `recommend.md` (short‑term guidance)

---

## Persistence

Memory is stored locally in a structured JSON file.

This allows:
- continuity across runs
- inspection and auditing
- future experimentation with salience or decay

---

## Scheduling

The agent is executed via a system scheduler (e.g., cron).

This enables:
- self‑initiated execution
- predictable cadence
- bounded autonomy
The agent does nothing between scheduled runs.
