# NomicLaw: Emergent Trust and Strategic Argumentation in LLMs during Collaborative Law-Making

**Authors:** Asutosh Hota, Jussi P.P. Jokinen  
**Affiliation:** University of Jyväskylä, Finland

This repository provides all code, data, and analysis pipelines for reproducing the results of our [AAAI/AIES 2025](https://aies-conference.com/) paper:

> **NomicLaw: Emergent Trust and Strategic Argumentation in LLMs during Collaborative Law-Making**

Please email: asutosh.jyu.hota@jyu.fi for any further information.

## Table of Contents

- [Project Overview](#project-overview)
- [Repository Structure](#repository-structure)
- [Setup & Requirements](#setup--requirements)
- [Running the Simulations](#running-the-simulations)
- [Data Folder Structure](#data-folder-structure)
- [Analysis Notebooks](#analysis-notebooks)
- [Contact](#contact)
- [License](#license)

---

## Project Overview

NomicLaw is a multi-agent simulation framework to study legal argumentation, negotiation, and alliance formation by Large Language Models (LLMs) in collaborative law-making scenarios. Agents (LLMs) respond to realistic legal vignettes, propose rules, justify them, and vote. The framework produces both quantitative and qualitative results, including strategic behavior metrics, clustering, and thematic analysis of AI-generated legal justifications.

---

## Repository Structure

nomiclaw/
<sub>Data folder (input vignettes, configs, and output results)</sub>

AIES_Qualitative_phase_1_final.ipynb
<sub>Qualitative analysis phase 1</sub>

extract_qualitative_data.ipynb
<sub>Extract & preprocess qualitative data from logs</sub>

nomiclaw_simulation.ipynb
<sub>Main LLM agent simulation script</sub>

quantitative_analysis.ipynb
<sub>Reproduce all quantitative metrics, plots & tables</sub>

thematic_qualitative_data.ipynb
<sub>Automated thematic coding (LLM + human validation)</sub>

Appendix.pdf/
<sub> Appendix showing vignettes, additional analysis supporting paper</sub>

README.md


---

## Setup & Requirements

1. **Python version:** 3.9+
2. **Recommended:** [Anaconda](https://www.anaconda.com/products/distribution) or `venv` for environment isolation.
3. **Install dependencies:**  
   Most notebooks specify their dependencies at the top (e.g. `pip install -r requirements.txt` if present).  
   Typical dependencies (install in terminal or cell):
   ```bash
   pip install pandas numpy matplotlib scikit-learn openpyxl
   pip install jupyter

Running the Simulations

Main Simulation Notebook:

1. Open nomiclaw_simulation.ipynb in Jupyter Lab or Notebook.

This will:

1. Save simulated data to nomiclaw/ data folder.

2. Run either homogeneous (same model) or heterogeneous (different models) group simulations as described in the paper.

3. Save results (proposals, votes, justifications, scores) in nomiclaw/.

4. Configurable settings: Number of rounds, agents, models etc. are set in code cells.

Input Data:

1. You can add your own vignettes by editing/adding files in the script.

LLM API/Model Requirements:

1. Simulations require access to local or remote LLMs (Ollama). Follow the instructions in notebook markdown cells.

Analysis Notebooks

quantitative_analysis.ipynb

    Computes all key behavioral and network metrics:

    Self-Vote Rate, Win Rate, Reciprocity, Coalition Switch Rate, Bloc Stability, PCA, clustering, and summary tables.

    Reproduces all result plots and tables for the paper.

extract_qualitative_data.ipynb

    Extracts justifications, votes, proposals from simulation logs.

    Outputs clean CSVs for qualitative/thematic coding.

AIES_Qualitative_phase_1_final.ipynb

    Manual and hybrid LLM-human thematic annotation and reliability checks.

    Cohen’s kappa and cross-rater reliability scripts included.

thematic_qualitative_data.ipynb

    Automated and semi-automated jurisprudential theme coding.

    Computes proposal–vote consistency, theme prevalence, etc.


(Optional) Tips for Reviewers & Users

    All config and setup is inline in the notebooks—no external config file required.

    All data and output paths are relative to the repo and nomiclaw/ folder.

    You may freely add new vignettes or modify agent/model parameters for extension studies.
