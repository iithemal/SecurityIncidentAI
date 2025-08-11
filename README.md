# SOCIntel
AI-based system for Security Incident Pattern Detection and Response Optimization.

# Security Incident Pattern Recognition and Response Optimization

This project applies AI techniques to **Wazuh** security incident data to recognize patterns, forecast threats, detect anomalies, and recommend optimized automated responses via **Shuffle** playbooks. It is deployed in a private cloud homelab environment, with results optionally visualized in **Grafana**.

---

## 🔍 Problem Statement
Modern Security Operations Centers (SOCs) face alert fatigue from tools like Wazuh, generating massive amounts of alerts daily. Manual triage is slow and error-prone. This project leverages AI to:
- Detect recurring threat patterns
- Predict incident surges
- Recommend automated response workflows
- Identify anomalies (potential zero-day threats)

---

## 🎯 Objectives
- Forecast incident trends using time-series models (Prophet/LSTM)
- Cluster similar alerts to identify recurring threats (KMeans/DBSCAN)
- Recommend Shuffle playbooks based on incident type
- Detect anomalies using Isolation Forest
- Provide an interactive dashboard for SOC analysts (Streamlit/Grafana)

---

## 🛠️ Home Lab Environment
This project runs in a **VMware private cloud** with the following components:

| Component     | Purpose                                                |
|---------------|--------------------------------------------------------|
| **Wazuh**     | Collects and indexes security logs from endpoints      |
| **Shuffle**   | Automates incident response workflows (SOAR)           |
| **Grafana**   | Visualizes trends, predictions, and recommendations    |
| **AI Engine** | Python-based ML models running locally or in a VM      |

### Network Topology
```
[Endpoints/Agents] --> [Wazuh Manager] --> [AI Engine] --> [Shuffle SOAR] --> [Automated Actions]
                                                |
                                                +--> [Grafana for Visualization]
```

---

## 📊 Dataset Plan
**Primary Source:**
- Wazuh alerts via REST API:
  - `timestamp`, `rule_id`, `alert_type`, `asset_id`, `message`

**Augmentation:**
- MITRE ATT&CK mappings
- CVE vulnerability feeds

**Feature Engineering:**
- Time-based features (hour, day, frequency)
- Encoded categorical variables (`alert_type`, `rule_id`)
- NLP features from alert messages (TF-IDF / transformers)

---

## ⚙️ AI Pipeline
1. **Data Ingestion**
   - Fetch alerts from Wazuh API
2. **Preprocessing**
   - Cleaning, feature extraction, encoding, NLP processing
3. **Modeling**
   - Forecasting: Prophet / LSTM
   - Clustering: KMeans / DBSCAN
   - Classification: Random Forest / Logistic Regression
   - Anomaly Detection: Isolation Forest
4. **Recommendation Engine**
   - Map incidents to Shuffle playbooks
5. **Integration**
   - Send recommendations to Shuffle via API
6. **Visualization**
   - Streamlit dashboard
   - Grafana for operational monitoring

---

## 🔗 API Integrations

### **Wazuh API**
- Used to fetch alerts
- Authenticated using token-based authentication

### **Shuffle API**
- Used to trigger pre-defined playbooks based on AI recommendations

### **Grafana API** (Optional)
- Push metrics for visualization or read dashboards programmatically

---

## 🖥️ Development Environment Setup
```bash
# Create virtual environment
conda create -n secai python=3.10 -y
conda activate secai

# Install dependencies
pip install pandas numpy scikit-learn prophet matplotlib seaborn sentence-transformers streamlit requests
```

---

## 📅 Project Timeline

| Week | Deliverables |
|------|--------------|
| 1 | Problem statement, objective, dataset plan, proposal |
| 2 | Data preprocessing & feature engineering |
| 3 | Model building & evaluation |
| 4 | Final integration with Shuffle & Grafana, presentation |

---

## 📦 Folder Structure
```
SecurityIncidentAI/
├── data/                # Sample / exported Wazuh data
├── proposal/            # Project proposal document
├── notebooks/           # Jupyter notebooks for modeling
├── scripts/             # Python scripts for integration & automation
└── README.md
```

---

## 📈 Evaluation Criteria
- **Proposal & Planning**: 20
- **Implementation & Innovation**: 30
- **Functionality & Evaluation**: 20
- **Final Report & Presentation**: 20
- **Timely Submissions**: 10
- **Bonus** (multi-source data, XAI, blog): +10

---

## 📌 Future Enhancements
- Incorporate Explainable AI (SHAP/LIME) to justify recommendations
- Add reinforcement learning for adaptive playbook selection
- Real-time streaming from Wazuh to AI Engine
- Multi-cloud deployment

---
