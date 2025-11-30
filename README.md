SaaS Churn Analysis Dashboard

> A Power BI dashboard that transforms churn data into actionable retention strategies for a B2B SaaS company

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Formulas-orange)](https://dax.guide/)

![Dashboard Screenshot](link-to-your-screenshot.png)

 Business Problem

A fictional B2B SaaS company offering three subscription tiers (Basic, Pro, and Enterprise) was experiencing rising cancellations and revenue loss. Leadership identified a critical gap: they could see *that* customers were churning, but lacked visibility into *why* it was happening, *which* segments were most affected, and *who* was at risk next.

Without this intelligence, the Customer Success and Growth teams were stuck in reactive mode—responding to cancellations after the fact rather than preventing them.

## Solution

An interactive Power BI dashboard built to answer five critical business questions:

1. **How is churn trending?** Track customer and revenue churn month-over-month
2. **What's the financial impact?** Quantify MRR lost to churn and calculate net revenue churn
3. **Which segments churn most?** Compare churn rates across Basic, Pro, and Enterprise tiers
4. **Why are customers leaving?** Break down churn by reason (competition, budget, support, pricing, features)
5. **Who's at risk right now?** Identify accounts with early warning signals (low usage, support tickets, declining satisfaction)

The dashboard transforms raw subscription, usage, support, and payment data into a unified retention command center for Customer Success and Growth teams.

---

## Key Findings

### Current State
| Metric | Value | MoM Change |
|--------|-------|------------|
| Churn Rate | 25.40% | +15.9% |
| Net Revenue Churn | 3.46% | +224.4% |
| Retention Rate | 74.60% | -12.7% |
| MRR Lost | $386K | +318.7% |

### Critical Insights

**Enterprise Tier Crisis**
- Enterprise customers (highest contract value) show disproportionately high churn
- Despite generating the most revenue per customer, this tier has retention issues
- Suggests product-market fit problems or inadequate support for complex enterprise implementations
- Immediate priority: Enterprise customer health review and dedicated success resources

**Revenue Impact Accelerating**
- MRR loss growing 3x faster than customer churn (+318.7% MoM vs +15.9%)
- This divergence indicates larger accounts (likely Pro and Enterprise) churning, not just Basic plan customers
- $386K in MRR lost this month alone
- Net revenue churn at 3.46% puts the company above the healthy threshold of <2% for B2B SaaS

**Early Warning Signals**
- At-risk accounts display three consistent behavioral patterns:
  - **Low product usage**: Less than 30% of purchased seats/features being used
  - **Support ticket volume**: 3+ tickets filed in the 30 days before churn
  - **Declining satisfaction**: NPS scores dropping below 6/10
- These indicators appear 2-4 weeks before formal cancellation notices
- Opportunity: Customer Success can intervene proactively using this data

**Churn Drivers by Frequency**
1. **Competition** (32% of churned customers) - Competitors offering better features or more intuitive UX
2. **Budget constraints** (28%) - Economic pressure forcing customers to cut software spending
3. **Poor support experience** (18%) - Slow response times and unresolved technical issues
4. **Pricing concerns** (13%) - Perceived value doesn't match cost, especially in Pro tier
5. **Missing features** (9%) - Product gaps preventing customers from achieving their goals

*Note: Competition and budget are external pressures, while support, pricing, and features are internally controllable.*

---

## Dashboard Components

### 1. Executive Summary View
- Real-time churn and retention KPIs with MoM trends
- Revenue churn vs. customer churn comparison
- Quick filters by date range, plan tier, and customer segment

### 2. Churn Deep Dive
- **Customer Churn Trend**: Month-over-month churned customer tracking
- **Revenue Churn Trend**: MRR loss visualization over time
- **Plan Tier Analysis**: Churn distribution across Basic, Pro, and Enterprise
- **Churn Reason Breakdown**: Root cause analysis (support, budget, competition, pricing, features)

### 3. Predictive At-Risk View
Interactive table highlighting customers likely to churn based on:
- Low satisfaction scores (<6/10)
- Elevated support ticket volume
- Declining product usage
- Payment delays or issues

---

## Technical Implementation

**Built With:**
- Power BI Desktop (data modeling & visualization)
- DAX (calculated measures and KPIs)
- Power Query (data transformation)

**Data Model:**
- 5 related tables in a star schema:
  - **Customers** (demographic and account info)
  - **Subscriptions** (plan tier, start date, cancellation date, MRR)
  - **Usage** (product engagement metrics, seat utilization)
  - **Support** (ticket volume, resolution time, satisfaction scores)
  - **Payments** (billing history, payment delays)
- Proper one-to-many relationships between fact and dimension tables
- Date table with fiscal calendar for time intelligence calculations

**Key DAX Measures:**
```
Churn Rate = 
DIVIDE(
    [Churned Customers],
    [Total Customers Previous Month],
    0
)

Net Revenue Churn = 
DIVIDE(
    [MRR Lost] - [MRR Expansion],
    [MRR Previous Month],
    0
)
```

---

## Project Structure

```
├── README.md
├── dashboard/
│   └── SaaS_Churn_Dashboard.pbix
├── data/
│   └── sample_data.csv (fictional dataset)
├── documentation/
│   ├── project_background.md
│   ├── metrics_definition.md
│   └── data_dictionary.md
└── screenshots/
    ├── overview.png
    └── at_risk_customers.png
```

---

## Documentation

- **[Project Background](documentation/project_background.md)** - Business context and objectives
- **[Metrics Definition](documentation/metrics_definition.md)** - How each KPI is calculated
- **[Data Dictionary](documentation/data_dictionary.md)** - Complete data schema reference

---

## How to Use

1. Download the `.pbix` file from the `dashboard/` folder
2. Open in Power BI Desktop
3. (Optional) Connect to your own data source following the schema in the data dictionary
4. Interact with filters to explore churn patterns by segment, time period, or reason

---

## Business Applications

This dashboard framework can be adapted for:
- **Customer Success teams** to prioritize outreach to at-risk accounts
- **Product teams** to identify feature gaps driving churn
- **Executive leadership** to track retention health and revenue impact
- **Sales teams** to understand competitive threats

---

## Future Enhancements

- [ ] Predictive churn scoring using machine learning
- [ ] Cohort retention analysis
- [ ] Integration with customer health score data
- [ ] Automated email alerts for high-risk accounts
- [ ] Churn recovery tracking (win-back campaigns)

---



This project uses fictional data for demonstration purposes.



\*\*Ayomide Ola-Gafar\*\*  

Built as part of a SaaS-focused portfolio showcasing data analytics and business intelligence skills.



