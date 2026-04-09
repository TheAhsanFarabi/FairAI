# FairAI

> *Measuring Bias and Fairness in LLMs via Human Evaluation*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![Status: Research](https://img.shields.io/badge/Status-Research-orange.svg)]()
[![Venue: Conference](https://img.shields.io/badge/Target-AAAI%20%7C%20FAccT%20%7C%20AIES-green.svg)]()

---

## 📌 Overview

**Fair AI** is a research project that investigates how Large Language Models (LLMs) reason about moral dilemmas — and how that reasoning compares to human judgment. Rather than a simple agree/disagree comparison, Fair AI introduces a rigorous, multi-dimensional evaluation pipeline covering:

- 🔁 **Prompt sensitivity analysis** — does moral judgment change with framing?
- 🧑‍🤝‍🧑 **Human alignment measurement** — do LLMs decide like humans do?
- 🧠 **Ethical framework classification** — are LLMs utilitarian, deontological, or something else?

---

## 🧪 Models Evaluated

| Model | Provider | Type |
|---|---|---|
| GPT-4 / GPT-4o | OpenAI | Proprietary |
| Claude 3 (Opus / Sonnet) | Anthropic | Proprietary |
| Gemini 1.5 Pro | Google DeepMind | Proprietary |
| LLaMA 3 | Meta | Open-source |
| Mistral 7B / Mixtral | Mistral AI | Open-source |

---

## 🔬 Methodology

### 1. Scenario Bank
A curated set of **15–20 general moral dilemma scenarios** spanning five tension types:
- Harm vs. Duty
- Individual vs. Collective Good
- Fairness vs. Loyalty
- Autonomy vs. Paternalism
- Competing Responsibilities

Each scenario has a binary or ternary decision structure (Action A / Action B / Abstain).

### 2. Prompt Sensitivity Analysis
Each scenario is presented to every LLM using **4 distinct framings**:

| Framing | Description |
|---|---|
| 🟦 Neutral | Bare scenario, no perspective imposed |
| 🟥 Emotional | Emphasizes personal affect and responsibility |
| 🟨 Legal | Frames the situation through rules and liability |
| 🟩 Stakeholder | Perspective of an affected party |

Each prompt is run **3 times per model** to measure within-model decision stability.

### 3. Human Participant Study
- **60–100 participants** recruited via Prolific / university pool
- Each participant evaluates a randomized subset of **8–10 scenarios** (neutral framing)
- Data collected: decision, free-text justification, confidence (1–5 Likert)

### 4. Ethical Framework Coding
All LLM and human justifications are coded into four frameworks:

| Framework | Key Markers |
|---|---|
| ⚖️ Utilitarian | outcomes, majority benefit, consequences |
| 📜 Deontological | duties, rules, rights, "regardless of outcome" |
| 🏛️ Fairness-based | equality, impartiality, justice |
| 🤝 Responsibility-based | role obligations, causal proximity |

Human responses are coded by **two independent raters** (target Cohen's κ ≥ 0.70).

### 5. Alignment Metrics
- Percent agreement per model per scenario
- Cohen's κ between each LLM and the human distribution
- Jensen-Shannon Divergence across full decision distributions

---

## 🚀 Running Experiments

```bash
# Run LLM prompt sensitivity experiments
python experiments/prompt_sensitivity/run_llm_eval.py --model gpt-4o --scenarios data/scenarios/

# Compute stability scores
python analysis/stability_scores.py --results results/llm_outputs/

# Compute human alignment metrics
python analysis/alignment_metrics.py --human data/human_survey/ --llm results/llm_outputs/

# Generate ethical framework distributions
python analysis/framework_distribution.py
```

---

## 📊 Key Results

> ⚠️ *Results will be updated upon paper acceptance.*

| Model | Human Agreement (%) | Cohen's κ | Dominant Framework |
|---|---|---|---|
| GPT-4o | — | — | — |
| Claude 3 | — | — | — |
| Gemini 1.5 | — | — | — |
| LLaMA 3 | — | — | — |
| Mistral 7B | — | — | — |

---


---

## 👥 Human Study Ethics

This study involves human participants and has been reviewed under institutional ethical guidelines. All participant data is:
- Fully anonymized before storage
- Collected with informed consent
- Not linked to any personally identifiable information

---

## 📬 Contact

For questions, collaboration inquiries, or access to the scenario bank, please open an issue or contact the authors via the repository.

