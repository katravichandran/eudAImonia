# EudAImonia

Code and data for "EudAImonia: Epistemic Governance in Large Language Models to Reduce Hallucination and Sycophancy," a senior thesis submitted to the Departments of Computer Science and Philosophy at Harvard College (2026).

## Overview

This repository contains all experimental code and raw results for Chapter II of the thesis, which implements and evaluates the Epistemic Governance Norm of Assertion (EGNA) across five frontier models: GPT-4o mini, GPT-4o, GPT-5.1, Gemini 2.0 Flash, and Claude Sonnet 4.

All experiments were run via the Harvard HUIT API proxy at temperature 0.7, 3 iterations per prompt. GPT-5.1 outputs were constrained to 30 words per response due to API token requirements; this constraint was applied uniformly across all experimental conditions for that model.

## Repository Structure

| File | Experiment | Thesis Section |
|---|---|---|
| `fake_template_baseline.ipynb` | Baseline responses to fake article prompts | II.B |
| `fake_template_egna.ipynb` | EGNA scaffold responses to fake article prompts | II.B |
| `fake_template_control.ipynb` | Control scaffold responses to fake article prompts | II.D |
| `real_template.ipynb` | Baseline and EGNA responses to real article prompts | II.E |
| `sycophancy.ipynb` | Baseline and EGNA responses to normative-identity prompts | III |
| `motivating_examples.ipynb` | Illustrative examples referenced in Chapter II introduction | II.A |

## Data Files

| File | Description |
|---|---|
| `fake_template_baseline_results.xlsx` | Raw outputs for fake template baseline |
| `fake_template_egna_results.xlsx` | Raw outputs for fake template EGNA scaffold |
| `fake_template_control_results.xlsx` | Raw outputs for fake template control scaffold |
| `real_template_baseline_results.xlsx` | Raw outputs for real template baseline |
| `real_template_egna_results.xlsx` | Raw outputs for real template EGNA scaffold |
| `sycophancy_baseline_results.xlsx` | Raw outputs for sycophancy baseline |
| `sycophancy_egna_results.xlsx` | Raw outputs for sycophancy EGNA scaffold |

## Scaffolds

**EGNA Scaffold** — two-stage epistemic partition:
- Stage I classifies propositions as KNOWN, NOT_KNOWN, or RISK
- Stage II asserts only from KNOWN and explicitly marks NOT_KNOWN content

**Control Scaffold** — two-stage epistemic reflection without partition:
- Stage I asks what the model knows and what its limits are
- Stage II responds with a truthfulness norm but no hard gate

## Requirements
```python
pip install pandas openpyxl tenacity requests
```

Requires a valid `HUIT_API_KEY` environment variable. Designed to run in Google Colab.
