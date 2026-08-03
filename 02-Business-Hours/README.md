
# Salesforce Business Hours Configuration

## Project Overview

This project demonstrates how to configure Salesforce Business Hours for a global organization.

The goal is to ensure that Salesforce calculates service response times, SLAs, and case escalations based on actual working hours instead of 24/7 calendar time.

---

# Business Scenario

## Company: ABC Solutions

ABC Solutions provides customer support services across multiple regions.

The company uses Salesforce Service Cloud to manage customer Cases.

The support leadership team has the following requirements:

- SLA calculations should consider only working hours.
- Weekends should not count toward response time.
- Regional support teams should have different working schedules.
- Company holidays should be excluded from SLA calculations.

---

# Business Requirements

## Support Centers

ABC has three support locations:

| Region | Time Zone | Working Hours |
|---|---|---|
| USA Support | Eastern Time (EST) | Monday-Friday, 9:00 AM-5:00 PM |
| India Support | India Standard Time (IST) | Monday-Friday, 9:00 AM-6:00 PM |
| UK Support | Greenwich Mean Time (GMT) | Monday-Friday, 8:00 AM-5:00 PM |

---

# Business Analysis

Before configuring Salesforce, the following questions were discussed:

| Requirement | Business Decision |
|---|---|
| Should weekends count toward SLA? | No |
| Should holidays count toward SLA? | No |
| Do all regions have the same working hours? | No |
| Are separate Business Hours required? | Yes |
| Should SLA calculations use Business Hours? | Yes |

---

# Salesforce Solution

## Configuration Created

The following Business Hours records were created:

### 1. USA Support Hours

```
Name:
USA Support Hours

Time Zone:
Eastern Time

Working Days:
Monday-Friday

Hours:
9:00 AM - 5:00 PM
```

---

### 2. India Support Hours

```
Name:
India Support Hours

Time Zone:
India Standard Time

Working Days:
Monday-Friday

Hours:
9:00 AM - 6:00 PM
```

---

### 3. UK Support Hours

```
Name:
UK Support Hours

Time Zone:
GMT

Working Days:
Monday-Friday

Hours:
8:00 AM - 5:00 PM
```

---

# Salesforce Configuration Steps

## Step 1: Navigate to Setup

1. Login to Salesforce.
2. Click the Gear icon.
3. Select Setup.

---

## Step 2: Open Business Hours

Navigate:

```
Setup
→ Company Settings
→ Business Hours
```

---

## Step 3: Create Business Hours

Click:

```
New Business Hours
```

Enter:

- Business Hours Name
- Time Zone
- Working Days
- Working Hours

Save the configuration.

---

# Holiday Configuration

## Business Requirement

Company holidays should not count toward SLA calculations.

Configured holidays:

| Holiday | Date |
|---|---|
| New Year's Day | January 1 |
| Independence Day | July 4 |
| Thanksgiving | November |
| Christmas Day | December 25 |

---

# Real-Time SLA Scenario

## Requirement

A customer creates a High Priority Case.

SLA:

**8 Business Hours**

Case Created:

Friday 4:00 PM

Support Hours:

Monday-Friday  
9:00 AM-5:00 PM

---

## Salesforce Calculation

Friday:

```
4 PM - 5 PM = 1 Business Hour
```

Remaining:

```
7 Business Hours
```

Monday:

```
9 AM - 4 PM = 7 Business Hours
```

SLA Due:

```
Monday 4:00 PM
```

---

# Testing and Validation

## Test Case Created

| Field | Value |
|---|---|
| Case Priority | High |
| Created Date | Friday 4:00 PM |
| SLA Requirement | 8 Business Hours |
| Business Hours Used | USA Support Hours |

Expected Result:

Case should expire on Monday at 4:00 PM.



<img width="800" height="176" alt="image" src="https://github.com/user-attachments/assets/a8eb39b5-d0ab-4d17-9b0c-dcb5cb10ba42" />


<img width="1656" height="374" alt="image" src="https://github.com/user-attachments/assets/3ee81366-a16c-4afc-b488-4f4aebc97568" />


<img width="1657" height="485" alt="image" src="https://github.com/user-attachments/assets/3446d2f8-e20e-4646-aca0-0b31711164cd" />


<img width="1268" height="602" alt="image" src="https://github.com/user-attachments/assets/dbd486ad-394d-41e4-b3b7-6b774a0c55ce" />








---
