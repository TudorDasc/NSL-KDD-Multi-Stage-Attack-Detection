# NSL-KDD-Multi-Stage-Attack-Detection
Based on the dataset NSL-KDD, I trained a Histogram-based Gradient Boosting Classification Tree to classify and identify the attack stages from the dataset.

## Multi-Stage Attack Detection Dashboard (NSL-KDD)

An Intrusion Detection System (IDS) prototype that trains a multi-class classifier on the NSL-KDD dataset, extracts temporal-style features, detects potential multi-stage attack sequences, maps detections to MITRE ATT&CK techniques / kill-chain stages, and exports results to an interactive HTML dashboard.

## Features

- **Multi-class attack detection** (5 classes)
  - Normal, DoS, Probe, R2L, U2R
- **Temporal feature extraction** (rolling-window style signals such as bursts/spikes)
- **Multi-stage sequence detection**
  - Flags likely progressions like reconnaissance → exploitation and DoS distraction patterns
- **MITRE ATT&CK mapping**
  - Maps detected attack types to technique IDs and approximated kill-chain stages
- **Interactive dashboard**
  - Charts (Chart.js), sequence cards, and a timeline view with “jump to window” highlighting
- **Exportable results**
  - Produces `dashboard_data.json` consumed by the dashboard

## Project Structure

```text
.
├── ids_dashboard.html              # Dashboard UI (loads dashboard_data.json)
├── analysis.py                     # Main training + analysis + export script (your Python pipeline)
├── dashboard_data.json             # Generated output for the dashboard (created after running analysis)
├── dataset/
│   ├── KDDTrain+.txt
│   └── KDDTest+.txt
└── README.md
