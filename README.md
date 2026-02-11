Here’s your **GitHub README** content rewritten cleanly and professionally, keeping the same structure and style for your project.

---

# PRISM-Insurance-Dashboard


---

## Problem Statement

This dashboard helps the insurance company understand customer feedback and overall satisfaction levels. It enables the company to identify key areas where customers are satisfied and where improvements are required.

By analyzing ratings across different services, the company can focus on weak areas to improve customer experience and retention. The dashboard also provides insights into customer distribution, policy preferences, and service performance, helping management make better data-driven decisions.

If a higher percentage of customers are neutral or dissatisfied, the company must prioritize service quality improvements.

---

## Steps Followed

* **Step 1:** Loaded the dataset into Power BI Desktop (CSV/Excel file).
* **Step 2:** Opened Power Query Editor and enabled *Column Distribution*, *Column Quality*, and *Column Profile* under the View tab.
* **Step 3:** Switched profiling to “Based on Entire Dataset” for accurate analysis.
* **Step 4:** Checked for missing or error values and handled null values where necessary.
* **Step 5:** Ignored null values while calculating averages where they were minimal and not impactful.
* **Step 6:** Selected a suitable theme under the View tab in Report View.
* **Step 7:** Added slicers for important fields such as:

  * Policy Type
  * Customer Type
  * Age Group
  * Claim Status
* **Step 8:** Added card visuals to display key KPIs like:

  * Total Customers
  * Total Premium Amount
  * Average Claim Amount
  * Customer Satisfaction Score
* **Step 9:** Created bar and pie charts to show:

  * Customer satisfaction distribution
  * Policy type distribution
  * Claim status breakdown
* **Step 10:** Added rating visuals to represent different service parameters such as:

  * Claim Processing
  * Customer Support
  * Policy Benefits
  * Transparency
  * Overall Service Rating

While calculating average ratings, values marked as not applicable (or 0) were excluded.

* **Step 11:** Inserted text boxes for company name and tagline.
* **Step 12:** Added company logo and design elements using shapes and images.

---

## DAX Calculations

### 1️⃣ Age Group (Calculated Column)

```DAX
Age Group = 
IF(InsuranceData[Age] <= 25, "0-25",
IF(InsuranceData[Age] <= 50, "25-50",
IF(InsuranceData[Age] <= 75, "50-75",
"75+")))
```

---

### 2️⃣ Total Customers (Measure)

```DAX
Total Customers = COUNT(InsuranceData[CustomerID])
```

---

### 3️⃣ Percentage of Customers (Measure)

```DAX
% Customers = 
DIVIDE([Total Customers], CALCULATE([Total Customers], ALL(InsuranceData))) * 100
```

---

### 4️⃣ Total Premium Collected (Measure)

```DAX
Total Premium = SUM(InsuranceData[PremiumAmount])
```

---

### 5️⃣ Total Claim Amount (Measure)

```DAX
Total Claims = SUM(InsuranceData[ClaimAmount])
```

---

## Dashboard Snapshot

<img width="1329" height="737" alt="Image" src="https://github.com/user-attachments/assets/85606a1b-7c0a-44ff-866d-26e5467150e8" />

---

Key KPIs
•	Total Premium Amount: 5.98M
•	Total Coverage Amount: 600.55M
•	Total Claim Amount: 16.91M

# Key KPIs Snapshot

<img width="940" height="126" alt="Image" src="https://github.com/user-attachments/assets/b91217bb-5848-4477-911d-2c193a1f088a" />

Customer Distribution
•	Female Customers: 5,001
•	Male Customers: 5,003

# Customer Distribution Snapshot

<img width="564" height="273" alt="Image" src="https://github.com/user-attachments/assets/e28fe5d6-b6a2-466d-9ad4-3dfb584a781e" />

Policy Type – Premium Amount
•	Travel: 2.5M
•	Health: 1.2M
•	Auto: 1.0M
•	Life: 0.7M
•	Home: 0.6M
Travel policies generate the highest premium revenue.

# Policy Type – Premium Amount Snapshot

<img width="686" height="355" alt="Image" src="https://github.com/user-attachments/assets/905019e0-4352-43d0-9451-3269dfabad08" />

Customer Status
•	Active: 5.82K (58.13%)
•	Inactive: 4.19K (41.87%)
Majority of customers are active.

# Customer Status Snapshot

<img width="694" height="359" alt="Image" src="https://github.com/user-attachments/assets/72f74320-a893-4a46-98e6-99d10b4f5e90" />

Number of Claims by Status
•	Rejected: 4.4K
•	Settled: 3.4K
•	Pending: 2.3K
Rejected claims are higher compared to settled and pending claims.

# Number of Claims by Status Snapshot

<img width="575" height="459" alt="Image" src="https://github.com/user-attachments/assets/ac28f68d-5a77-4607-b8b9-01e6f21b7c9d" />

Claim Amount by Age Group
•	Adult: 8.8M
•	Elder: 6.4M
•	Young Adult: 1.7M
Adults contribute the highest claim amount.

#Claim Amount by Age Group Snapshot

<img width="689" height="372" alt="Image" src="https://github.com/user-attachments/assets/de72418e-0c7f-4145-ab98-37335e2cc12b" />

Claim Status by Policy Type
Policy Type	Pending	Rejected	Settled
Auto	2,08,10,615.30	4,06,71,711.59	3,29,84,558.70
Health	2,76,82,791.20	5,24,01,928.42	4,00,17,100.67
Home	1,30,01,816.73	2,74,06,202.63	2,06,45,568.43
Life	1,72,59,587.93	3,37,22,751.49	2,31,21,204.63
Travel	5,72,47,694.90	10,73,95,611.51	8,61,82,353.59
Total	13,60,02,506.05	26,15,98,205.64	20,29,50,786.03
Travel policies have the highest claim values across all statuses.


Insights
1.	Travel policies contribute the highest premium revenue.
2.	Adults generate the highest claim amount (8.8M).
3.	Rejected claims (4.4K) are significantly high and need investigation.
4.	58% of customers are active, which shows stable retention.
5.	Male and female customers are almost equally distributed.


Conclusion
This dashboard provides a complete overview of premium performance, claim trends, and customer activity. It helps management identify high-claim segments, improve settlement ratios, and make data-driven decisions for better profitability and service quality.

