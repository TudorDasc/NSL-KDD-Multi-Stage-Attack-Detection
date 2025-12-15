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
  - A timeline view with “jump to window” highlighting
- **Exportable results**
  - Produces `dashboard_data.json` consumed by the dashboard

## Project Structure

```
.
├── ids_dashboard.html              # Dashboard UI (loads dashboard_data.json)
├── ids_prediction.ipynb            # Main training + analysis + export script (your Python pipeline)
├── dashboard_data.json             # Generated output for the dashboard (created after running analysis)
├── KDDTrain+.txt
├── KDDTest+.txt
├── README.md
```

## Running the tool
1. Install requirements: ```pip install -r requirements.txt```
2. Run the analysis pipeline from ```ids_prediction.ipynb```
3. Run a local web host ```python -m http.server 8000 ```
4. Access ```http://localhost:8000/visualization.html```
5. Explore the visualization!


## Visualization

### Brief Description

<img width="1889" height="958" alt="image" src="https://github.com/user-attachments/assets/1627050e-f6e4-45eb-a456-d808f3ae22d4" />

### MITRE Breakdown

<img width="1829" height="539" alt="image" src="https://github.com/user-attachments/assets/2a65ca4a-a956-4c9c-bb4e-a647564deccb" />

### Temporal Features and Over Time Detection

<img width="1831" height="546" alt="image" src="https://github.com/user-attachments/assets/4d7a83c1-8001-46b1-a6e3-1591697c94ec" />

### Multi-Stage Description with Severity Score

<img width="1826" height="424" alt="image" src="https://github.com/user-attachments/assets/69f64c47-2a26-4511-b464-004418a08212" />

<img width="1823" height="325" alt="image" src="https://github.com/user-attachments/assets/3daf4dd5-7dcc-4f87-87fb-b539fa085014" />

### Techniques Detected and Timeline Visualization
<img width="1673" height="640" alt="image" src="https://github.com/user-attachments/assets/aafda418-5018-424b-8173-cb836b165dfb" />

