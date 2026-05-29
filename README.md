# AI Cyber Defense Threat Intelligence Platform

A mini SOC/SIEM-style platform inspired by tools like Splunk, CrowdStrike, Elastic SIEM, and IBM QRadar.

## Project Goal
Build an end-to-end cyber defense platform that can:

- Collect logs from systems and services
- Analyze suspicious activity
- Detect potential attacks with rule-based + ML approaches
- Visualize threats in real time
- Trigger alerts and optional auto-response actions

## Repository Structure

```text
AI-Cyber-Defense-Threat-Intelligence-Platform/
├── backend/
│   └── .gitkeep
├── frontend/
│   └── .gitkeep
└── README.md
```

## Planned Components

### Frontend
- React dashboard
- Real-time threat feed
- Severity charts and trends
- Alert panel and suspicious IP tracking

### Backend
- FastAPI (recommended) or Node.js + Express
- Log/event ingestion APIs
- Detection orchestration and alert management
- WebSocket endpoints for live updates

### ML Layer
- Python + scikit-learn/pandas/numpy
- Initial models: Isolation Forest, Random Forest, Logistic Regression
- Initial use cases: brute-force detection, abnormal login attempts, DDoS-like spikes

### Data & Search
- PostgreSQL for users, alerts, and history
- Elasticsearch for large-scale log search and analytics

## High-Level Architecture

1. Simulated/real traffic generates logs
2. Collectors send events to the backend
3. Backend stores events and invokes detection logic
4. Detection results are pushed to frontend in real time
5. Optional response engine blocks malicious activity

## Suggested Development Roadmap

1. **Phase 1:** Basic ingestion + dashboard
2. **Phase 2:** Real-time updates and alerting
3. **Phase 3:** ML-based anomaly detection
4. **Phase 4:** Honeypot integration
5. **Phase 5:** Auto-response (IP blocking/reporting)

## Notes

- Start small and iterate.
- Validate all attack simulations only in your own lab/local environment.
- Keep architecture modular so each team can work independently.
