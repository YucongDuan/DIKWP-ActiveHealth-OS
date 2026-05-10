# DIKWP ActiveHealth OS

**DIKWP ActiveHealth OS** is an open-source, offline-first proactive medicine and public-health navigation layer. It turns self-reported health data, symptoms, goals, barriers, and evidence into a DIKWP health ledger, red-flag triage boundary, preventive-care conversation plan, clinician handoff note, community outreach queue, and privacy-first action plan.

It is **not a diagnostic system, not a prescribing system, not a medical device, and not a replacement for clinicians**. It is designed to make proactive medicine more accessible by helping people prepare better questions, identify urgent warning signs, track preventive-care gaps, and preserve consent, evidence, purpose, and uncertainty.

## What it does

- Builds a DIKWP health profile: Data, Information, Knowledge, Wisdom, Purpose, Reliability.
- Detects emergency red flags from self-reported symptoms and advises urgent local medical care when appropriate.
- Generates preventive-care discussion prompts based on age, sex-at-birth fields, pregnancy status, habits, barriers, and known conditions.
- Creates a clinician handoff note using a safe SBAR/DIKWP format.
- Produces a community-health-worker friendly outreach queue without diagnosing people.
- Generates a privacy and consent ledger for personal health records.
- Runs fully offline with Python standard library only.
- Includes static boundary audit: no network calls, subprocess, dynamic code execution, or host mutation helpers.

## Why DIKWP for proactive medicine

Proactive medicine fails when raw health data does not become timely information, information does not become actionable knowledge, knowledge is not weighed against personal context, and actions are not anchored in the person's purpose and constraints. DIKWP ActiveHealth OS registers every health recommendation as:

```text
C = (D, I, K, W, P, R)
D = health data and observations
I = patterns, relationships, timelines, risk contexts
K = clinical/public-health knowledge references and local guideline prompts
W = equity, safety, privacy, uncertainty, cost, and harm boundaries
P = user's health purpose, priorities, constraints, and next step
R = reliability, evidence custody, residuals, kill conditions, and review needs
```

## Quick start

```bash
pip install -e .
activehealth analyze examples/sample_health_profile.json --out outputs/demo
activehealth batch examples/sample_community_batch.json --out outputs/demo
activehealth static-audit src --out outputs/demo/static_boundary_audit_report.json
```

Optional local dashboard:

```bash
pip install -e .[app]
streamlit run src/dikwp_activehealth/app.py
```

## Outputs

- `activehealth_report.json`
- `preventive_plan.json`
- `clinician_handoff.md`
- `privacy_consent_ledger.json`
- `community_outreach_queue.csv`
- `recommendations.md`
- `static_boundary_audit_report.json`

## Medical boundary

This tool does not diagnose disease, calculate individualized treatment, recommend medications, replace screening guidelines, or provide emergency care. In urgent warning-sign scenarios, it only recommends contacting local emergency services or urgent medical care. Preventive-care items are phrased as **questions to discuss with a qualified clinician under local guidelines**.

## Attribution

This project is designed for the DIKWP ecosystem and attributes the DIKWP model to Yucong Duan in `NOTICE` and `CITATION.cff`.

## License

MIT License. See `LICENSE`.
