# Case Replay Example: Insider Trading Risk (SIG-001)

This example details how a specific raw signal (`SIG-001`) from `sample-data/signals_raw.csv` is processed step-by-step by CasePilot AI.

## Step 1: Raw Ingestion
- **Signal ID**: `SIG-001`
- **Telemetry**: `User J. Doe mentioned 'getting ahead of the announcement' in encrypted channel #trading-floor.`
- **Severity**: High

## Step 2: Triage Assessment
The Triage Agent processes the raw signal and generates the following structured output:
```json
{
  "escalate": true,
  "risk_score": 9,
  "reasoning": "Communication mentions 'getting ahead of the announcement' on the trading floor, which is a strong indicator of insider information handling.",
  "entities": {
    "actors": ["j.doe"],
    "assets": [],
    "systems": ["chat_monitor", "#trading-floor"]
  },
  "suggested_category": "Insider Trading"
}
```

## Step 3: Review Analysis
The Reviewer Agent cross-references company policy `SEC-10b-5 Compliance Guideline` and maps the incident:
- **Finding**: User J. Doe is on the restricted trading list for Project Phoenix.
- **Timeline**: The communication occurred 2 days before the scheduled earnings release.
- **Recommendation**: Immediate suspension of user's trading credentials and initiation of a formal interview.

## Step 4: Executive Report
The Report Agent produces a markdown report summary:
> ### Compliance Incident Report
> **Incident ID**: INC-2026-001  
> **Status**: Escalated  
> **Risk Level**: Critical  
> **Summary**: Unauthorized discussion of non-public financial announcements in public trading floor channel by J. Doe.
