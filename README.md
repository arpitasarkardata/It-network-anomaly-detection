# 🔍 IT Network Traffic — Anomaly Detection

## 📌 Project Overview

IT companies managing large infrastructure face a critical challenge — detecting unusual 
network behavior before it causes downtime or security breaches.

This project builds an **end-to-end anomaly detection pipeline** on real network packet 
capture data — from raw CSV ingestion to an interactive dashboard flagging suspicious traffic.

---

## 🛠 Tools Used

| Tool | Purpose |
|---|---|
| Python | Core analysis and modelling |
| pandas | Data cleaning and manipulation |
| scikit-learn | Isolation Forest anomaly detection model |
| Plotly | Interactive dashboard |
| matplotlib / seaborn | Static EDA charts |
| openpyxl | Excel export |
| Jupyter Notebook | Development environment |

---

## 🗂 Dataset

**Network Traffic Dataset** — Real packet capture data from Kaggle

| Column | Description |
|---|---|
| Time | Timestamp of each network packet |
| Source | Sender IP address |
| Destination | Receiver IP address |
| Protocol | Network protocol (TCP, TLS, DNS, ARP etc.) |
| Length | Packet size in bytes |
| Info | Packet description |

---

## 🔍 Analysis Structure

### 1. Data Cleaning
- Removed nulls and duplicates
- Label encoded categorical columns (Source, Destination, Protocol)

### 2. Exploratory Data Analysis
- Protocol distribution across all packets
- Packet length trends over time
- Top 10 most active source IP addresses

### 3. Anomaly Detection Model
- Algorithm: **Isolation Forest** (unsupervised ML)
- Contamination rate: 5%
- Features used: Time, Packet No., Length, Source, Destination, Protocol

### 4. Dashboard & Export
- Interactive 4-panel Plotly dashboard saved as HTML
- Results exported to Excel with 3 sheets: All Traffic, Anomalies Only, Summary

---

## 📊 Key Findings

| Metric | Value |
|---|---|
| Total Packets Analysed | 3,94,136 |
| Normal Packets | 3,74,439 |
| Anomalous Packets | 19,697 |
| Anomaly Percentage | 5.0% |
| Most Common Protocol | TCP |

---

## 📈 Visualisations

| Chart | Insight |
|---|---|
| Packet Length vs Time | Anomalies cluster around high-length spikes |
| Protocol Distribution | TCP dominates at ~65% of all traffic |
| Anomaly Count Pie | 5% of packets flagged as anomalous |
| Top 10 Source IPs | A few IPs generate disproportionately high traffic |

---

## 💡 Business Relevance

This project directly maps to real IT operations work:

1. **Infrastructure Monitoring** — Flags unusual traffic before it causes downtime
2. **Security Analysis** — Identifies suspicious IPs and protocols automatically
3. **Scalable Framework** — Pipeline can be extended to live network streams

---

## ▶️ How to Run

1. Clone this repository
```
git clone https://github.com/arpitasarkardata/it-network-anomaly-detection.git
```

2. Install required libraries
```
pip install pandas numpy matplotlib seaborn scikit-learn plotly openpyxl
```

3. Place `Midterm_53_group.csv` in the same folder

4. Run **Kernel → Restart & Run All** in Jupyter Notebook

---

## 📁 Repository Structure
```
it-network-anomaly-detection/
    anomaly_detection.ipynb     ← Full analysis notebook
    anomaly_dashboard.html      ← Interactive Plotly dashboard
    anomaly_results.xlsx        ← Excel report (3 sheets)
    README.md                   ← This file
```

---

## 📂 Dataset Source

Network Traffic Dataset — available on [Kaggle](https://www.kaggle.com/datasets/ravikumargattu/network-traffic-dataset)

---

*Built by Arpita Sarkar — B.Tech ECE, Kalyani Government Engineering College*
