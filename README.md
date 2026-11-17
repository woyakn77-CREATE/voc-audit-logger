# VOC Audit Logger

**Live demo:** https://woyakn77-create.github.io/voc-audit-logger/ · [Back to portfolio](https://woyakn77-create.github.io/Portfolio/)

A phone-first tool for auditing shop work areas for volatile organic compounds (VOCs). Photograph a product label, AI identifies the product and classifies it against the US EPA VOC definition (40 CFR 51.100(s)), the auditor reviews the result, and it goes into a log that exports as CSV in the audit template's column order.

## How it works
1. **Check:** a label photo or product name goes to Claude with a structured prompt. Claude returns JSON: product, VOC status (Yes / No / Exempt / Unclear), category, VOC content if published, confidence, reason, and what to confirm on the SDS.
2. **Review:** the result pre-fills the log form; the auditor confirms quantity, container size, SDS on file and storage condition.
3. **Log and export:** entries are grouped by audit category and copy out as CSV.

## Demo mode
As built, the AI check runs inside Claude and needs a Claude sign-in. This public demo includes four sample label photos (generic, drawn in code) and a list of 33 common shop chemicals with built-in reference results, so it works for anyone. Built-in values are typical figures for generic products; always confirm on the actual SDS.

## Design choices
- Audit categories match the assignment: solvents, chemicals, degreasing, vanishing oils, soldering, SMC/BMC.
- EPA-exempt compounds (acetone, methyl acetate, PCBTF, perchloroethylene) are called out, with a note that exempt does not mean safe.
- Low-confidence identifications are flagged for SDS verification.

## Tools
HTML/JavaScript · Claude (vision + structured JSON output) · prompt design

## Files
`index.html`: the whole app, one self-contained file.
