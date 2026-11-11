# Report Generator (Antigravity / Gemini Edition)

**A Google Antigravity (Gemini) harness: drop in a data file, ask in one sentence, and a five-role agent team produces a full business report.**

English · [한국어](README.ko.md)

```
data prep → analysis → visualization → writing → executive summary & review → HTML report
```

## Output

`report.html` (a single self-contained report you can open and print), plus `01`–`05` Markdown files: data, analysis with calculation log, chart spec with inline SVG, full report, and executive summary with a review checklist. Results are copied to `Desktop/보고서_결과물` and `Downloads/보고서_결과물`, and the folder opens automatically.

## Requirements

Google Antigravity (desktop app) and Python 3.10+ (the agent installs it if missing). No paid API keys.

## Quick start

Paste into the Antigravity chat:

```text
Clone https://github.com/AI-in-2hour/report-generator, read SKILL.md in that folder first and follow it. Using the samples/kingo-healthcare data, quickly build an executive report on Kingo Healthcare's Vietnam entry strategy.
```

Or clone the repo and open the folder as an Antigravity workspace; `GEMINI.md` applies automatically.

Put your own files in `input/`. Do not put confidential company data, personal data, or passwords in it; check your company's AI policy first. The `samples/` data is fictional.

## License and attribution

- Licensed under the [Apache License 2.0](LICENSE).
- Derived from `ko/82-report-generator` in [revfactory/harness-100](https://github.com/revfactory/harness-100) (Apache-2.0, Copyright 2026 Robin).
- Antigravity / Gemini modifications by AI-IN ([AI-in-2hour](https://github.com/AI-in-2hour), 2026-11). See [NOTICE](NOTICE); every modified file carries a change notice at the top.
- This repository is not affiliated with or endorsed by the original author.
