[简体中文](README.md) · English

# amber-opencode

> ⚠️ **Correction (2026-10-02, second)**: one defense case, A-d511f9e8, is now NA on every lane (the exam room did not grade the file the model gave in, and the grader asks for something the task text does not say). The denominator and the **number of passed cases do not change**; every lane's total now carries `'`. In this repo's issue tables, read that cell as NA. Everything else stays as published; the [correction notice](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-02-a-d511f9e8.en.md) governs.

> ⚠️ **Correction (2026-10-02)**: the papers below were answered by a model that left its own paper and touched grading material; they count neither as a pass nor as a fail. deepseek-flash @ OpenCode Go: 2 papers (A-24bcf707, A-8d4bc770) now NA, board score 17/24 → **15'/24**. The cause was an isolation fault in our exam setup; the fault is ours. The rest of this page stays as published; where they differ, the [correction notice](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-02.en.md) governs.

> **2026-10-07 update**: A-cdc3d11a (review): On one review case the grader counted every sub-point of a well-formed finding as a separate unproven claim and treated real defects outside its short answer list as false alarms, so a correct, well-formatted review could not reach the passing line; the case is held on every lane, denominator unchanged, until the grader and exam room are repaired and the case is re-sat. This lane (deepseek-flash @ OpenCode Go) the cell goes from a loss to NA (held); the case moves from a loss to NA on 27 lanes and no sitting is re-run. The pass count is unchanged (15'/24 on the board); losses go 6→5 and NA 3→4; the review axis stays 1/2 with 1 NA. The OpenCode Go cell in the matrix of the [W37 issue](results/2026-W37.md) is updated accordingly. See the [amber spec repo correction of 2026-10-07 (A-cdc3d11a)](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-07-a-cdc3d11a.en.md).

Public periodic [AMBER](https://github.com/getaskclaw/amber) benchmark results of models served by OpenCode Go (opencode.ai/zen/go). **Cases stay private; results are public.**

## What this is

- A 'lane' is one vendor's shop/API for a model name; a 'case' is one task, a 'run' is one sitting (a case with more than one variant has more runs).
- One `results/YYYY-Www.md` per issue: same cases, same harness (the program that runs the exam and scores it), full library per model; same model name across vendors side by side.
- Each issue pins: library size and hashes, per-case defect-hunt score and pass/fail, terminal states (how the run ended), token usage (when the lane reports it) and latency, environment fingerprint, and a verdict written under evidence rules.
- Cases, oracles, transcripts (full answer logs)s and intermediates are **never published**.
- Sister repos: [amber-deepseek](https://github.com/getaskclaw/amber-deepseek) (official DeepSeek lane), [amber-commandcode](https://github.com/getaskclaw/amber-commandcode) (CommandCode lane), [amber-gpt](https://github.com/getaskclaw/amber-gpt), [amber-crof](https://github.com/getaskclaw/amber-crof), [amber-ollama](https://github.com/getaskclaw/amber-ollama), [amber-devin](https://github.com/getaskclaw/amber-devin), [amber-workbuddy](https://github.com/getaskclaw/amber-workbuddy) (WorkBuddy ACP lane), [amber-doubao](https://github.com/getaskclaw/amber-doubao), [amber-goldenpotato](https://github.com/getaskclaw/amber-goldenpotato), [amber-kimi](https://github.com/getaskclaw/amber-kimi), [amber-stepfun](https://github.com/getaskclaw/amber-stepfun). This repo's benchmark axis is **same-name cross-vendor duels** — the same model name on OpenCode Go / CommandCode / the official DeepSeek API can be a different endpoint, and every cross-repo citation carries an explicit date and band.

## Publication red lines

1. Publish only: scores and totals, token usage (when reported), speed, verdicts.
2. Never publish: case content, oracles/graders, transcripts, candidate workspaces, anything that could rebuild a case.
3. Every issue pins: model ID, effort band (the thinking-effort setting), date (UTC), harness version, per-case bundle hash — checkable against the public hash index in [amber](https://github.com/getaskclaw/amber).
4. Case numbering is private: public matrices use stable aliases (A-xxxxxxxx, hash-derived) plus bundle hashes only.
5. Tone: community measurement, not vendor attacks.

## A methods note

Same model name, same provider, two runs can still score differently — inference parameters, load, and server-side versions drift. Relay/aggregator lanes add an upstream routing layer: the same name may not be the same endpoint. Every conclusion here is dated and banded, and we re-test on a fixed rhythm. A single day's number is a snapshot, not a law.

## Results index

| Issue | Content | Headline |
|---|---|---|
| [2026-W37](results/2026-W37.md) | deepseek-flash (V4.1 GA) full-library debut (23 cases, GA day) | See the issue for scores and verdicts; all three same-name lanes verified genuine v4.1; strong build/ops, with the no-tools phantom-tool-call disease on review/vision papers |
| [2026-W38 correction notice](results/2026-W38-correction.en.md) | W38 full-library review: 0 cells reversed · 3 held here | 3 W37 ocgo-column cells held; the 16/23 headline may move up |

## Disclaimer

Not affiliated with or sponsored by OpenCode or DeepSeek. Scores are dated, band-specific snapshots, not buying advice.