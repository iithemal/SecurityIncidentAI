# Security Incident Pattern Recognition and Response Optimization

This project applies AI techniques to security incident data (simulated Wazuh logs) to recognize patterns, forecast threats, and optimize incident response using Shuffle playbooks.

## 🔍 Problem Statement
SOCs struggle with alert fatigue from tools like Wazuh. This project aims to reduce noise and improve response time by applying machine learning to predict, cluster, and automate alert handling.

## 🎯 Project Objective
- Forecast incident trends using LSTM/Prophet
- Cluster alerts using KMeans/DBSCAN
- Recommend response playbooks (via supervised learning)
- Detect anomalies with Isolation Forest
- Provide insights through a Streamlit dashboard

## 📊 Dataset Plan
- Simulated Wazuh logs (`timestamp`, `rule_id`, `alert_type`, `asset_id`, `message`)
- Time-based, categorical, and NLP-based features
- Augmented with external threat feeds (optional)

## 📅 Week 1 Deliverables
- ✅ Problem statement
- ✅ Project objective
- ✅ Dataset structure and plan
- ✅ Proposal PDF

## 📁 Folder Overview
- `data/`: Placeholder for simulated logs
- `proposal/`: Contains the Week 1 proposal document

---

**Note:** This project is part of the IIT Minor AI program and will evolve week-by-week. Code and models will be added in future milestones.
