
# Salesforce Fiscal Year Configuration

## Project Overview

This project demonstrates how to configure Salesforce Fiscal Year settings for a multinational organization.

The goal is to align Salesforce reporting, forecasting, and revenue tracking with the company's financial calendar.

---

# Business Scenario

## Company: GlobalTech Solutions

GlobalTech Solutions is implementing Salesforce Sales Cloud.

The Finance department follows a financial year that does not match the standard calendar year.

### Business Requirement

The company follows:

**Fiscal Year Start:** April 1  
**Fiscal Year End:** March 31

The Finance team requires Salesforce reports, dashboards, and forecasts to follow this financial calendar.

---

# Business Analysis

Before configuring Salesforce, the following requirements were gathered:

| Requirement | Business Decision |
|------------|------------------|
| Financial year start month | April |
| Financial year end month | March |
| Accounting calendar type | Standard monthly calendar |
| Reporting should follow fiscal periods | Yes |
| Forecasting should follow fiscal periods | Yes |

---

# Salesforce Solution

## Configuration Selected

### Fiscal Year Type

**Standard Fiscal Year**

### Fiscal Year Start Month

**April**

---

# Why Standard Fiscal Year?

The company only needs to change the starting month.

They still follow normal calendar months:

- April
- May
- June
- July
- etc.

A Custom Fiscal Year is not required.

---

# Fiscal Quarter Structure

After configuration, Salesforce automatically creates:

| Fiscal Quarter | Months |
|---------------|--------|
| Q1 | April - June |
| Q2 | July - September |
| Q3 | October - December |
| Q4 | January - March |

---

# Salesforce Configuration Steps

## Step 1: Navigate to Setup

1. Login to Salesforce.
2. Click the Gear icon.
3. Select Setup.

---

## Step 2: Open Fiscal Year Settings

Navigate:

```
Setup
→ Company Settings
→ Fiscal Year
```

---

## Step 3: Configure Fiscal Year

Update:

```
Fiscal Year Type:
Standard Fiscal Year

Start Month:
April
```

Save the changes.

---

# Testing and Validation

To validate the configuration:

## Create Sample Opportunities

| Opportunity | Close Date | Amount |
|------------|------------|--------|
| ABC Software Deal | May 15, 2026 | $100,000 |
| XYZ Enterprise Deal | August 20, 2026 | $150,000 |
| DEF Cloud Deal | February 10, 2027 | $200,000 |

---

# Report Validation

Created an Opportunity Report grouped by:

```
Close Date → Fiscal Quarter
```

Expected Result:

| Opportunity | Fiscal Quarter |
|------------|----------------|
| ABC Software Deal | Q1 |
| XYZ Enterprise Deal | Q2 |
| DEF Cloud Deal | Q4 |

---

# Business Impact

Before Configuration:

- Reports followed calendar year.
- Finance had to manually adjust reports.
- Forecasting did not match accounting periods.

After Configuration:

- Salesforce reports match Finance requirements.
- Forecasting aligns with fiscal periods.
- Revenue tracking becomes accurate.
- Leadership dashboards show correct quarterly performance.

---
