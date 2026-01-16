# 📊 Partner Program Risk Metrics Analysis

**Period: July - December 2025**
**Report Generated: January 15, 2026**

---

> **Note:** This is an example output from the `gep-risk-metrics-monthly-report.mdc` skill.
> The data shown is illustrative of the report format and structure.

---

## 📈 6-Month Portfolio Summary

| Metric                          | Value        |
| ------------------------------- | ------------ |
| **Total Dollars Processed**     | $839,267,482 |
| **Total Dollars Failed**        | $7,589,693   |
| **Weighted Failure Rate**       | **0.90%** ✅ |
| **Active Companies (Dec '25)**  | 10,939       |
| **Total Employees (Dec '25)**   | 40,405       |
| **Total Contractors (Dec '25)** | 4,686        |

> **Overall Assessment:** The portfolio is performing within healthy parameters with a failure rate under 1.0%.

---

## 📅 Monthly Trend Analysis

| Month    | Processed    | Failed     | Fail Rate | Trend                |
| -------- | ------------ | ---------- | --------- | -------------------- |
| Jul 2025 | $147,638,745 | $1,328,482 | 0.90%     | —                    |
| Aug 2025 | $133,301,925 | $1,209,273 | 0.91%     | ⬜ Stable            |
| Sep 2025 | $143,827,520 | $1,558,048 | 1.08%     | ⚠️ Elevated          |
| Oct 2025 | $150,576,516 | $1,153,009 | 0.77%     | ✅ Improved          |
| Nov 2025 | $136,777,051 | $1,414,302 | 1.03%     | ⚠️ Slightly Elevated |
| Dec 2025 | $227,145,725 | $1,926,579 | 0.85%     | ✅ Good              |

> **Key Insight:** December showed highest volume (year-end payroll surge) but maintained healthy failure rate at 0.85%.

---

## 💳 Payment Type Distribution (6-Month)

| ACH Speed     | Processed    | % of Total | Failed     | Fail Rate    |
| ------------- | ------------ | ---------- | ---------- | ------------ |
| **1-Day ACH** | $115,142,687 | 13.7%      | $565,416   | **0.49%** ✅ |
| **2-Day ACH** | $529,271,584 | 63.1%      | $4,021,738 | **0.76%** ✅ |
| **4-Day ACH** | $194,853,211 | 23.2%      | $3,002,539 | **1.54%** ⚠️ |

> **Critical Pattern:** 4-Day payments show **2-3x higher failure rates** than Fast ACH. This is a known structural pattern where slower collection windows correlate with higher payment failures.

---

## 🏢 Partner-Level Metrics

### Top 10 Partners by Processed Volume

| Partner             | Total Processed (6M) | Dec '25 Processed | Active Co. | Fail Rate | Risk         |
| ------------------- | -------------------- | ----------------- | ---------- | --------- | ------------ |
| **GoCo**            | $341,730,725         | $69,936,400       | 475        | 0.60%     | ✅ Low       |
| **Collective**      | $146,468,146         | $32,569,560       | 4,826      | 1.78%     | ⚠️ Elevated  |
| **Lattice Payroll** | $89,424,557          | $18,942,759       | 15         | 0.69%     | ✅ Low       |
| **Vagaro**          | $71,837,469          | $14,036,046       | 1,543      | 0.56%     | ✅ Low       |
| **Remote.com**      | $61,679,106          | $12,123,642       | 40         | 0.26%     | ✅ Excellent |
| **HR for Health**   | $67,283,007          | $17,570,270       | 344        | 0.16%     | ✅ Excellent |

---

## 🚨 Risk Flags & Standouts

### 🔴 Critical Issues

| Partner                    | Issue                               | Dec '25 Rate | 6M Average | Action Required                          |
| -------------------------- | ----------------------------------- | ------------ | ---------- | ---------------------------------------- |
| **Lettice Financial Labs** | October spike: **10.22%** fail rate | 0.28%        | 2.34%      | Single $292K failed payment. Monitor.    |

### ⚠️ Partners Requiring Attention

| Partner          | Issue                        | Latest Rate | Concern                                 |
| ---------------- | ---------------------------- | ----------- | --------------------------------------- |
| **Collective**   | High 4-Day ACH concentration | 2.07% (Dec) | 43% of GEP, 81.7% on 4-Day ACH          |

### ✅ Strong Performers

| Partner           | 6M Failure Rate | Notes                          |
| ----------------- | --------------- | ------------------------------ |
| **HiBob Payroll** | 0.00%           | Perfect record, $24M processed |
| **Remote.com**    | 0.26%           | Strong controls                |
| **HR for Health** | 0.16%           | 99.7% on Fast ACH              |

---

## 📋 Leadership Summary: 5 Key Findings

### 1. 🎯 **Critical: Collective remains highest concentration risk**

- 4,826 companies (43% of GEP portfolio)
- 81.7% on 4-Day ACH with 1.78% failure rate
- **Recommendation:** Prioritize Fast ACH migration initiative

### 2. ⚠️ **Lettuce Financial Labs October spike resolved**

- October saw 10.22% failure rate due to single payment failure
- Recovered to 0.28% in December
- **Status:** Monitoring only

### 3. 📊 **4-Day ACH shows structurally higher failures**

- 4-Day: 1.54% failure rate vs 0.76% for 2-Day
- **Implication:** ACH migration directly reduces risk

### 4. ✅ **Anchor partners performing well**

- GoCo (largest by volume): 0.60% failure rate
- HR for Health: 0.16% with 99.7% Fast ACH adoption

### 5. 📈 **December volume surge handled successfully**

- $227M processed (54% above monthly average)
- 0.85% failure rate (below 6M average)

---

## ✅ Recommended Actions

| Priority  | Action                                       | Owner                  | Timeline |
| --------- | -------------------------------------------- | ---------------------- | -------- |
| 🔴 **P0** | Initiate Collective Fast ACH migration pilot | Partner Success + Risk | Q1 2026  |
| 🟡 **P1** | Deep dive on Lattice November spike          | Risk Ops               | This Week|
| 🟢 **P2** | Document migration playbook                  | Partner Success        | Feb 2026 |

---

## 📎 Data Sources

- **Query 104845:** GEP Fail Percentage Analysis
- **Query 143614:** Fast ACH Month-over-Month Summary
- **Query 143613:** Current ACH Speed by Partner

---

_This example demonstrates the output format of the GEP Risk Metrics Monthly Report skill._
