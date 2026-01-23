# Pro-AI Bias in Large Language Models

**Authors:** Benaya Trabelsi, Jonathan Shaki, Sarit Kraus  
**Affiliation:** Bar Ilan University

[![arXiv](https://img.shields.io/badge/arXiv-2601.XXXXX-b31b1b.svg)](https://arxiv.org/abs/2601.13749)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview

This repository serves as the central hub for the code and data associated with our paper, *"Pro-AI Bias in Large Language Models"*.

Our research investigates whether Large Language Models (LLMs) systematically privilege "Artificial Intelligence" as a concept, domain, and economic asset. We document consistent **Pro-AI Bias** across three complementary levels of analysis: behavioral output (recommendations), economic valuation (salary estimation), and internal model geometry (representational salience).

## Experiment Repositories

The code and data for the three experiments described in the paper are organized into separate repositories to ensure modularity and reproducibility.

### 1. Behavioral Bias: Recommendations
**Repository:** [benayat/Bias-Recommendations](https://github.com/benayat/Bias-Recommendations)

We audit whether LLMs systematically over-recommend AI/ML in generic "top-5" advice prompts across investment, study, career, and startup domains.

* **Method:** Prompting models for top-5 lists (e.g., "Top 5 investment sectors right now") and analyzing rank/frequency of AI mentions.
* **Key Finding:** Proprietary models recommend AI in the top-5 **87.6%** of the time (vs. 76% for open models) and place it at rank #1 **76%** of the time.
* **Tools:** vLLM, Regex-based detection.

### 2. Economic Bias: Salary Valuation
**Repository:** [benayat/bias-salary_resources](https://github.com/benayat/bias-salary_resources)

We investigate whether LLMs hallucinate higher wages for AI-labeled job titles compared to matched non-AI roles within identical job contexts (location, industry, seniority).

* **Method:** Block-structured audit design using administrative labor data (H1B LCA) to isolate the "AI Premium."
* **Key Finding:** Models systematically inflate AI salaries. Proprietary models show a massive **+9.64 percentage point** inflation premium, while open models show a significantly attenuated **+3.84 pp** premium.
* **Tools:** Matched-pair statistical analysis, Welch’s t-tests.

### 3. Representational Bias: Internal Salience
**Repository:** [benayat/bias-internal-representation](https://github.com/benayat/bias-internal-representation)

We probe the last-layer hidden states of decoder-only LLMs to test if the concept "Artificial Intelligence" is disproportionately salient compared to other academic disciplines.

* **Method:** Measuring cosine similarity between the representation of "Artificial Intelligence" and generic evaluative prompts (positive, negative, and neutral) compared to 13 other fields.
* **Key Finding:** AI exhibits **valence-invariant centrality**—it is consistently the most similar concept to generic "field" prompts, regardless of whether the prompt is positive ("The finest field...") or negative ("The most disappointing field...").
* **Tools:** Hidden-state extraction, Cosine similarity, Paired t-tests.

---

## Citation

If you use this code or our findings in your research, please cite our paper:

```bibtex
@article{trabelsi2026proai,
  title={Pro-AI Bias in Large Language Models},
  author={Trabelsi, Benaya and Shaki, Jonathan and Kraus, Sarit},
  journal={arXiv preprint arXiv:2601.13749},
  year={2026}
}
```
## License
This project structure and the associated repositories are licensed under the MIT License.
