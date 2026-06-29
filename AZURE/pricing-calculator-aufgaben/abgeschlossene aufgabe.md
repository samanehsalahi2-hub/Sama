# 🌐 Azure Pricing Exercises — Complete Cost Analysis (Tasks A–F)

This document contains full calculations, cost comparisons, and optimization insights for Azure VM, Disk, Storage, Region, Redundancy, and Licensing scenarios.

---

# 🟦 Task A — VM + Disk + Hours Reduction

## 1. VM Cost for 730 Hours (B2s, Windows, West Europe)

- **Compute:** $35.04 / month  
- **OS (Windows License Included):** $5.84 / month  

**➡ VM Total = $40.88 / month**

---

## 2. Disk Cost (Standard HDD, 128 GiB)

- **Disk:** $5.89 / month

---

## 3. VM Cost for 160 Hours



\[
40.88 / 730 \approx 0.056\ \text{USD/hour}
\]





\[
160 \times 0.056 = 8.96\ \text{USD}
\]



---

## 4. Savings (730h → 160h)



\[
40.88 - 8.96 = 31.92\ \text{USD saved}
\]



---

## ✅ Summary (Task A)

| Item | Cost |
|------|------|
| VM (730h) | **$40.88** |
| Disk | **$5.89** |
| VM (160h) | **$8.96** |
| Savings | **$31.92** |

---

# 🟩 Task B — Pay‑as‑you‑go vs Azure Hybrid Benefit (D2s v3, Windows)

## 1. Pay‑as‑you‑go

- **Compute:** $87.60  
- **OS License Included:** $67.16  

**➡ Total = $154.76**

---

## 2. Azure Hybrid Benefit

- **Compute:** $87.60  
- **OS:** $0.00  

**➡ Total = $87.60**

---

## 3. Monthly Difference



\[
154.76 - 87.60 = 67.16\ \text{USD}
\]



---

## 4. Yearly Savings



\[
67.16 \times 12 = 805.92\ \text{USD}
\]



---

## 5. When Hybrid Benefit Makes Sense

- You already **own Windows Server licenses**  
- You want to **reduce OS licensing cost**  
- Long‑term workloads

---

## ✅ Summary (Task B)

| Model | Monthly Cost |
|-------|--------------|
| Pay‑as‑you‑go | **$154.76** |
| Hybrid Benefit | **$87.60** |
| Monthly Savings | **$67.16** |
| Yearly Savings | **$805.92** |

---

# 🟥 Task C — Region Comparison (B2ms, Linux, 730h)

## 1. Final Region Costs

| Region        | Compute | Disk | Total |
|---------------|---------|-------|--------|
| **West Europe**   | $70.08  | $5.89 | **$75.97** |
| **East US**       | $60.74  | $143.12* | **$203.86** |
| **Brazil South**  | $97.82  | $151.37* | **$249.19** |

\* Disk cost inferred from Azure Calculator totals.

---

## 2. Cheapest Region

**🟢 West Europe — $75.97**

---

## 3. Most Expensive Region + Percentage Difference



\[
(249.19 - 75.97) / 75.97 \times 100 \approx 228.2\%
\]



**➡ Brazil South is ~228% more expensive than West Europe**

---

## 4. Why Choose a More Expensive Region?

- Lower latency for users in that geography  
- Data residency laws  
- Compliance requirements  
- Customer proximity  
- Performance optimization

---

## ✅ Summary (Task C)

- Cheapest: **West Europe**  
- Most expensive: **Brazil South**  
- Brazil South is **~228%** more expensive  
- Higher cost often due to **latency, compliance, and user proximity**

---

# 🟪 Task D — VM + Managed Disk + Blob Storage (LRS vs GRS)

## 📌 Configuration

- **Region:** West Europe  
- **VM:** B2s, Windows, Pay‑as‑you‑go, 730h  
- **Managed Disk:** 128 GB Standard SSD  
- **Storage:** Blob Storage  
- **Redundancy:** LRS  
- **Data Stored:** 100 GB  
- **Write Ops:** 10,000 / month  
- **Read Ops:** 50,000 / month  

---

# 1) VM Cost + Storage Cost (LRS)

## VM Cost

- Compute: **$35.04**  
- OS: **$5.84**

➡ **VM Total = $40.88**

---

## Managed Disk Cost

- Standard SSD (128 GB): **$12.29**

---

## Storage Account (LRS)

| Operation Type | Quantity | Rate | Cost |
|----------------|----------|------|------|
| Write Ops | 10,000 | $0.050 per 10k | **$500.00** |
| Read Ops | 50,000 | $0.004 per 10k | **$200.00** |
| List/Create | 10 | $0.050 per 10k | **$0.50** |
| Other Ops | 1 | $0.004 per 10k | **$0.01** |
| Data Retrieval | 1000 GB | $0.000 | **$0.00** |
| Data Write | — | Free | **$0.00** |

➡ **Storage Total (LRS) = $702.58**

---

# 2) Total Monthly Cost (LRS)



\[
40.88 + 12.29 + 702.58 = 755.75\ \text{USD}
\]



➡ **Total Monthly (LRS) = $755.75**

---

# 3) Switching to GRS (Geo‑Redundant Storage)

Your GRS screenshot shows:

- Geo‑replication data transfer: **$20.00**  
- Additional GRS replication charges included  

➡ **Storage Total (GRS) = $1,225.58**

---

# 4) Total Monthly Cost (GRS)



\[
40.88 + 12.29 + 1,225.58 = 1,278.75\ \text{USD}
\]



➡ **Total Monthly (GRS) = $1,278.75**

---

# 5) Comparison: LRS vs GRS

| Mode | Storage Cost | Total Monthly |
|------|--------------|---------------|
| **LRS** | $702.58 | **$755.75** |
| **GRS** | $1,225.58 | **$1,278.75** |

### Difference



\[
1,225.58 - 702.58 = 523\ \text{USD}
\]





\[
523 / 702.58 \times 100 \approx 74.4\%
\]



➡ **GRS is ~74% more expensive than LRS**

---

# 🟦 Task E — Final Scenario

## 1. Given Values (from Azure Calculator)

- **VM1:** 78.11 USD  
- **VM2:** 19.13 USD  
- **Storage:** 5.04 USD  
- **SQL Database (Basic, DTU, 2 GB):** 4.90 USD  

---

## 2. Total Monthly Cost



\[
78.11 + 19.13 + 5.04 + 4.90 = 107.18\ \text{USD}
\]



➡ **Total = 107.18 USD / month**

---

## 3. Most Expensive Component

➡ **VM1 — 78.11 USD**

---

## 4. Reserved Instance for VM1 (1 Year)

Assuming ~41% discount:



\[
78.11 \times 0.59 = 46.09\ \text{USD}
\]





\[
78.11 - 46.09 = 32.02\ \text{USD saved/month}
\]



➡ **Monthly savings: 32.02 USD**

---

## 5. Yearly Cost Comparison

### PAYG



\[
107.18 \times 12 = 1,286.16\ \text{USD}
\]



### With Reserved VM1



\[
75.16 \times 12 = 901.92\ \text{USD}
\]



### Yearly Savings



\[
1,286.16 - 901.92 = 384.24\ \text{USD}
\]



➡ **Yearly savings: 384.24 USD**

---

# 🟦 Task F — Final Solution

## 1. Original Configuration (Calculator)

- **VM (D8s v3, Windows, 730h, Brazil South):** 732.92 USD  
- **Premium SSD (1 TB):** 233.47 USD  
- **Blob Storage (GRS, 50 GB):** 3.26 USD  

➡ **Total = 969.65 USD / month**

---

## 2. Cost Pitfalls

- Expensive region (Brazil South)  
- Oversized VM (D8s v3)  
- Premium SSD unnecessarily large  
- GRS instead of LRS  
- VM running 24/7 although app needs ~180h/month  

---

## 3. Cheaper Alternative

- Region: West Europe  
- VM: B2ms  
- Usage: 180h/month  
- Disk: Standard SSD 128 GB  
- Storage: LRS 50 GB  

➡ **Estimated total: 45–55 USD/month**

---

## 4. Price Comparison



\[
\text{Savings} = \frac{969.65 - 50}{969.65} \approx 0.948
\]



➡ **~95% cheaper**


