<div align="center">

# 🌩️ Indra.ai
**AI-Powered Parametric Income Protection for India's Gig Economy**

[![Phase: 1 (Seed)](https://img.shields.io/badge/DEVTrails_2026-Phase_1_(Seed)-0078D7?style=for-the-badge&logo=codeigniter)](#)
[![Concept: Agentic AI](https://img.shields.io/badge/Concept-Agentic_AI-black?style=for-the-badge)](#)
[![Status: Ideation](https://img.shields.io/badge/Status-Ideation-success?style=for-the-badge)](#)

*A submission for Guidewire DEVTrails 2026.*

</div>

---

##  The Problem
India's platform-based delivery partners (Zomato, Swiggy) are the backbone of our fast-paced digital economy. However, external disruptions—such as extreme monsoon floods, 45°C+ heatwaves, and sudden localized strikes—can reduce their working hours and cause them to lose **20-30% of their monthly earnings**. 

Currently, gig workers have no income protection against these uncontrollable events. When disruptions occur, they bear the full financial loss with no safety net.

## ⚡ The Solution: Indra.ai
**Indra covers broken shifts.** We are building an AI-enabled parametric insurance platform that safeguards gig workers against income loss. 


---
## 📉 Actuarial Model: Composite Risk Pricing
Indra utilizes a **Predictive Risk Engine** that recalculates the **Weekly Premium ($P_w$)** every 168 hours. The model moves away from static pricing to reflect the real-time volatility of the gig economy.

### The ML Inference Pipeline
1. **Feature Ingestion:** Ingests hyper-local historical disruption frequency ($Z_{risk}$) and 7-day multi-source atmospheric forecasts ($W_{forecast}$).
2. **Probability Mapping:** An XGBoost model outputs a probability score for specific disruption thresholds (e.g., rainfall > 10mm/hr).
3. **Weekly Premium Calculation:**:
   
  $$P_{w} = \left( \sum_{i=1}^{n} P(D_{i}) \cdot L_{i} \right) \cdot (1 + \text{Margin}_{ops}) - \delta_{trust}$$
   * **$P(D_i)$**: Probability of disruption $i$ occurring in the upcoming week.
   * **$L_i$**: Estimated income loss for the Food Delivery persona during that disruption.
   * **$\text{Margin}_{ops}$**: Operational loading to cover system overheads.
   * **$\delta_{trust}$**: Telemetry-based trust discount for verified active workers.

---

## 🤖 AI Architecture: The "Scout & Validator" System
Indra eliminates the traditional claims process via a **Dual-Agent AI architecture** for real-time trigger monitoring and automated payout initiation.

### Multi-Event Normalization
To prevent over-payment during simultaneous disasters, Indra utilizes a **Composite Disruption Index (CDI)**: 

$$CDI = \min \left( 1.0, \sum_{i=1}^{n} w_i \cdot \text{norm}(x_i) \right)$$
* This ensures payouts are normalized and capped at the total potential loss of income for the affected period, maintaining the platform's solvency.

### The Data Oracles:
* **Agent 1 (The Scout):** Uses LLM-based ingestion to monitor unstructured data (regional news, social feeds) for unplanned disruptions like strikes or curfews.
* **Agent 2 (The Validator):** Cross-references Scout findings with hard API data (OpenWeatherMap, IMD, and Google Maps/TomTom Traffic velocity) to verify disruptions.

---

## 🛑 Fraud Mitigation: Telemetry Trust
The system incorporates **Intelligent Fraud Detection** to neutralize fake claims and GPS spoofing.

* **Location & Activity Validation:** Indra builds a unique **"Telemetry Signature"** for each worker based on historical travel patterns (stop-start frequency at commercial vs. residential hubs).
* **Active Validation:** Payouts only trigger if the user’s real-time telemetry matches their established work signature in the window immediately preceding the disruption.
* **Integrity Checks:** The system uses anomaly detection to identify GPS spoofing or duplicate claim attempts by analyzing device sensor data.

---
