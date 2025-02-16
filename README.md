# TalentCLEF2025 Evaluation Script

This repository contains a simplified evaluation script designed for the [**TalentCLEF 2025** task](https://talentclef.github.io/talentclef/docs/talentclef-2025/task-summary/). The script loads a qrels file and a run file (both in TREC format), evaluates the run against the qrels using the Ranx evaluation framework, and prints a set of standard metrics to the console. You can download the TalentCLEF 2025 corpora in [Zenodo](https://doi.org/10.5281/zenodo.14002665)

## Overview

The evaluation script performs the following tasks:

1. **Input Parsing:**  
   Receives the following inputs via command-line arguments:
   - **qrels file:** A file in TREC format containing the relevance judgments (columns: `q_id`, `iter`, `doc_id`, `rel`).
   - **run file:** A file in TREC format containing the retrieval run (columns: `q_id`, `Q0`, `doc_id`, `rank`, `score`, and an optional `tag` column).
   - 
2. **Loading Data:**  
   The script loads the qrels and run files into appropriate objects without applying any additional filtering.

3. **Evaluation:**  
   Using the [Ranx](https://github.com/RunEval/ranx) library, it computes standard evaluation metrics such as MAP, MRR, NDCG, Precision@5, Precision@10, and Precision@100.

4. **Output:**  
   The computed evaluation metrics are printed directly to the console.

## Setting Up the Evaluation Environment

### Clone TalentCLEF Evaluation script repo
   Open your terminal and run:
   ```bash
   git clone https://github.com/yourusername/talentclef2025-evaluation.git
   cd talentclef2025-evaluation
   ```

### Create Python Environment

1. **Create the Virtual Environment:**
     ```bash
     python3 -m venv .env
     ```

2. **Activate the Virtual Environment:**
     ```bash
     source .env/bin/activate
     ```
3. **Install the Required Dependencies:**
   Then, run:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

After setting up your Python environment and downloading the script, you can run the evaluation as follows:

```bash
python talentclef_evaluate.py --qrels toy-data/qrels_toy.tsv --run toy-data/run2_toy.trec
```

Replace `toy-data/qrels_toy.tsv` and `toy-data/run2_toy.trec` with the actual paths to your qrels and run files. 

## Task Context

This evaluation script is developed specifically for the [**TalentCLEF 2025** task](https://talentclef.github.io/talentclef/docs/talentclef-2025/task-summary/).
