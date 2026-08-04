# MercadoLibre: Funnel and Cohort Retention Analysis

## Executive Summary

This project analyzes user behavior in a simulated e-commerce case based on MercadoLibre-style event data from January to August 2025.

I used SQL to reconstruct the customer journey from the first platform visit to purchase, identify the stages with the greatest user loss, and evaluate customer retention through cohort analysis.

The funnel analysis showed that the most important friction occurred during the intermediate purchase-intent stages, particularly between adding a product to the cart and beginning checkout. Retention also declined progressively from D7 to D28, indicating difficulty sustaining user engagement after registration.

The results support recommendations related to checkout optimization, segmented user-experience improvements, onboarding, and retention campaigns.

## Business Problem

The project addressed the following questions:

- At which stage of the purchase journey are the most users lost?
- What percentage of users advance from one event to the next?
- How does conversion vary by country, device, and acquisition source?
- How does retention evolve from D7 to D28?
- Which cohorts maintain the strongest engagement over time?

The objective was to identify both immediate conversion barriers and longer-term retention weaknesses.

## Dataset and Scope

The dataset contained user-event information from January to August 2025.

The customer journey included events such as:

- First visit
- Product view
- Add to cart
- Begin checkout
- Payment
- Purchase

The data also included segmentation variables such as:

- Country
- Device or operating system
- Acquisition source
- Registration date
- Event date

## SQL Approach

### 1. Funnel Construction

I used SQL Common Table Expressions to organize users according to the stages they completed.

`COUNT(DISTINCT user_id)` was used to prevent users with repeated events from being counted multiple times within the same stage.

The analysis calculated:

- Users by funnel stage
- Conversion between consecutive stages
- Cumulative conversion
- Abandonment rates
- Drop-off between events

### 2. Sequential Validation

The funnel was designed to respect the order of the customer journey.

This prevented users from being classified as converted when events occurred outside the expected sequence.

### 3. Segment Analysis

Conversion was compared by:

- Country
- Device or operating system
- Acquisition source

This helped identify whether lower performance was concentrated within specific user groups.

### 4. Cohort Retention

Users were grouped according to their registration period.

Retention was evaluated at:

- D7
- D14
- D21
- D28

This allowed the analysis to compare how engagement evolved among different cohorts.

## Key Findings

- The largest funnel friction appeared between `add_to_cart` and `begin_checkout`.
- Additional user loss was observed during the payment and purchase process.
- Conversion performance varied between countries, devices, and acquisition sources.
- Retention declined progressively from D7 to D28.
- Some cohorts maintained stronger engagement than others.
- The platform faced challenges in both completing purchases and sustaining repeat user activity.

The observed segment differences were descriptive. They should not be described as statistically significant unless a formal statistical test is performed.

## Business Recommendations

- Simplify the transition from cart to checkout.
- Review payment errors, form complexity, delivery information, and unexpected costs.
- Analyze lower-performing countries and devices separately to identify localized user-experience problems.
- Develop onboarding and re-engagement campaigns during the first 7 to 14 days.
- Monitor retention by cohort instead of relying only on aggregate user activity.
- Test checkout and payment improvements through controlled experiments.
- Connect retention data with revenue before drawing conclusions about customer lifetime value.

## Tools and Techniques

- SQL
- Common Table Expressions
- JOIN operations
- Conditional aggregation
- `COUNT DISTINCT`
- Funnel analysis
- Conversion and abandonment rates
- Cohort analysis
- D7–D28 retention
- Customer segmentation

## Visualizations

### Conversion Funnel

![Conversion Funnel](images/funnel_dropoff.png)

### Cohort Retention

![Cohort Retention](images/cohort_retention.png)

## Repository Structure

```text
sql/       SQL queries for funnel and cohort analysis
results/   Exported analytical results
images/    Funnel and retention visualizations
README.md  Project documentation
