# CasePilot AI - Demo Script

This document details the step-by-step procedure to demonstrate the capabilities of CasePilot AI to stakeholders.

## Prerequisites
- Sample data is loaded in `sample-data/signals_raw.csv`.
- API keys configured for the agent runtime.
- Terminal window open.

## Demo Flow

### Step 1: Raw Signal Ingestion
- **Action**: Open `sample-data/signals_raw.csv` and show the audience the raw compliance logs.
- **Narrative**: *"Here we have a stream of raw, unfiltered telemetry logs. They contain high-volume, noisy signals from different enterprise sources like chat logs and access logs."*

### Step 2: Running the Triage Agent
- **Action**: Run the triage script.
  ```bash
  python src/run_triage.py --input sample-data/signals_raw.csv
  ```
- **Narrative**: *"The Triage Agent reads these raw signals, filters out noise (like routine policy updates), and flags specific high-risk signals, extracting key entities like User J. Doe."*

### Step 3: Reviewer Agent Context Matching
- **Action**: Display the logs showing the Reviewer Agent pulling in relevant guidelines and evaluating the flagged incident.
- **Narrative**: *"The Reviewer Agent takes the flagged incident and compares J. Doe's communication pattern with SEC insider trading guidelines and internal SOPs. It confirms a high likelihood of violation."*

### Step 4: Final Report Generation
- **Action**: Show the output of the Report Agent.
- **Narrative**: *"Finally, the Report Agent compiles the technical findings into a clean, executive-ready report, ready to be reviewed by a human compliance officer."*
