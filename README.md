# 6822-Assignment
Assignment 1 submission for Regulatory Technology MH6822
---
Wong Joon Hoong
G2505242K
joonhoongwong@yahoo.com, jwong187@e.ntu.edu.sg

## Data portion contribution (per assignment brief, +5%)

**Collaborators on the data portion:** None. All work on the data portion is solo.

**Synthetic data:** The 42-row hand-curated transaction set in `Task3_data/synthetic_transactions.csv` was designed solely by the author to demonstrate the four jurisdictional differential cases (A–D) documented in `Task3_summary.md`. No transactions, fields, or scenarios were sourced from another student's dataset.

**Gathered data (live feeds):** The OFAC SDN XML (~19,000 records), UN Security Council Consolidated XML (~1,000 records), and SGD/USD FX rate are pulled from public regulator and market-data endpoints by `Task3_sanctions_refresh.py` and the FX refresh routine in `run_all.py`.

This project is built mainly using AI Tools, including Claude Code and Codex.

Prerequisites

Python 3.10 or newer (built and validated on Python 3.14)
Internet access for live FX refresh and OFAC/UN sanctions XML download (offline falls back to cached files in Task3_data/)
1. Install dependencies (from inside the Task 3 folder)

python -m pip install -r Task3_requirements.txt
2. Run the verifier + rebuild

python run_all.py
Expect to see three pass lines in the output:

ALL 4 DIFFERENTIAL CASES VERIFIED
ALL TRIGGER COVERAGE CHECKS PASSED
ALL STRUCTURING CHECKS PASSED
This refreshes sanctions/FX status, regenerates every CSV/PNG under Task3_data/, rebuilds Task3_notebook.ipynb, and writes Task3_submission.zip.

3. Open the GUI

Windows:

.\Open_Task3_GUI.bat
macOS / Linux (or any platform):

python -m streamlit run Task3_streamlit_app.py
Streamlit serves at http://localhost:8501 and opens the browser automatically. The GUI has five tabs: Transaction explorer, Ad hoc tester, Analyst triage, Source freshness, Model evidence.

4. Read the notebook

Open Task3_notebook.ipynb in Jupyter, VS Code, or GitHub's web preview. Outputs (tables and charts) are pre-baked, so the notebook is readable without re-execution. Hit "Run All" to refresh — the first code cell re-invokes the verifier as a subprocess.

Reference documents in the package

README.md — same quick-start as above
Task3_summary.md — one-page design summary
Task3_model_card.md — full model card (intended use, failure modes, regulatory references)
Task3_Flow_and_Logic.md — trigger logic walkthrough
