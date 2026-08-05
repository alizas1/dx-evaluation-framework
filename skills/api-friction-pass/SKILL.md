---
name: api-friction-pass
description: >-
  Walk an API's integrator-facing docs and spec like a first-time integrator.
  Surface where someone would get confused or fail to finish a real job. Use
  when checking public docs or a draft/preview before publishing.
---

# API friction pass

Read **only the integrator-facing surface in scope** — live public docs, or a frozen draft/preview pack the user names. No internal knowledge, repo, or team chat unless it is inside that pack. Find where a first-time builder would get confused, guess wrong, or fail to finish a real job.
## Workflow
### 1. Lock scope
Ask (if missing):
- Which docs URL, files, or spec are in scope?
- Is this live public docs, or a draft/preview pack? If draft: which files/URL count as the **only** surface?
- What job is the builder trying to finish? (one concrete outcome)
If scope is unclear, ask before reading deeply.
### 2. Purpose in one sentence
Complete: **"This API lets a developer ___."**
Write it from the outside — what someone can accomplish, not how the system works inside.
If you cannot finish that sentence confidently from the in-scope surface alone, that gap is itself a finding.
### 3. Pick 1–2 real jobs
Write 1–2 concrete scenarios a real integrator would attempt (not "use the API").
Example shape: "Create X, then update Y, then confirm Z from the response."
These jobs anchor the rest of the pass. When unsure whether something matters, ask: *would someone pursuing one of these jobs actually hit this?*
### 4. Walk like a builder
Using only the in-scope surface, try to see the path for those jobs. Prefer noticing anomalies ("that doesn't fit") over lecturing.
Use these prompts (skip any that don't apply):
- Can I authenticate and make a first successful call from what's in scope?
- Do names and descriptions match what the call actually does?
- If I follow the happy path, where do I have to guess?
- Are examples copy-pasteable, and do they match the contract?
- When something fails, do errors tell me what to do next?
- Could an agent finish from the machine-readable bits alone, or does the important shape live only in prose?
Stay with contradictions. If two surfaces in scope disagree, say so. If you need an answer that only exists outside the pack, that is a finding — do not fill it from insider knowledge.
### 5. Write findings
For each real issue:
- **What broke** — the concrete confusion or failure
- **Where** — page, endpoint, field, example, or spec path
- **Why it matters** — which job from step 3 it blocks or slows
Keep the list short. Drop nitpicks that would not affect those jobs.
End with the purpose sentence (or the gap if missing), the 1–2 jobs, and the findings.
## Tone
Clear, practical, spoken. Prefer noticing and wondering over "here's what I know." Sound like a careful colleague reading the docs cold.
