# Databel Customer Churn Analysis (Power BI)

This project walks through a customer churn analysis for Databel, a telecom provider, built in Power BI. The goal was to figure out who is churning, why, and which customer segments or account characteristics are most tied to churn, then bring the findings together into a set of interactive dashboard pages.

## Tools and data

Built entirely in Power BI Desktop, using DAX measures and calculated columns for the churn logic, and Power BI visuals (bar, line, map, matrix, scatter, and card visuals) for the reporting. The data came from an excel file file with fields covering demographics, account details, contract and payment info, service usage, and churn status.

All files including the Power BI workbook, data excel sheet, and dashboard graphics are all uploaded in the repository available for review.

## Process and key findings

### Data validation and churn rate
Before digging into anything, I checked that the customer ID count and the distinct customer ID count matched, which confirmed there were no duplicate records to worry about. From there I converted the churn boolean column(yes/no) into a binary dummy variable(1/0) to build out a churn rate measure. The overall churn rate for the dataset came out to 26.86%.

### Why customers are churning
Looking at churn reasons and categories together, competitor activity is the clear driver. Customers citing a better competitor offer or better competitor devices make up the top two reasons, and when grouped into categories, competitor related churn accounts for about 45 percent of all churned customers, well ahead of attitude, dissatisfaction, or price.

![image alt](https://github.com/Nintencode/Power-BI-Case-Study-Analyzing-Customer-Churn/blob/main/Churn%20Rate%20and%20Reasons%20Dashboard.png)

### Age and demographics
Churn rises steadily with age. Senior customers churn at about 38 percent, compared to roughly 23 to 25 percent for younger groups. Breaking age into 10 year bins made the trend even clearer, churn rate climbs fairly steadily from the 20s through the 70s and 80s, even though the customer base itself is concentrated in the 20 to 50 range.

![Churn rate by age bins](images/03_churn_by_age_bins.png)

### Contract type and gender
Contract length turned out to be one of the strongest factors in the whole dataset. Month to month customers churn at around 46 percent, compared to under 7 percent for customers on yearly contracts. Gender did not show a meaningful difference within either group.

![Churn rate by contract category and gender](images/04_churn_by_contract_gender.png)

### Group plans
Customers on a shared group plan pay noticeably less per month than customers with no group at all, and their churn rate is much lower as well. This suggests that group plans are doing double duty, they lower the bill and they appear to keep customers around longer.

### Unlimited data plans
Somewhat counterintuitively, customers on an unlimited data plan churn more than those without one, 32 percent versus 16 percent. That pattern holds even after breaking usage into consumption tiers, so the unlimited plan itself seems tied to churn risk rather than how much data someone actually uses.

![Churn rate for unlimited vs limited data plans](images/05_churn_unlimited_plan.png)

### International plans and geography
Customers who have an international plan but are not actively using it churn at a very high rate, over 71 percent, while customers who are actively using their international plan churn far less. Geographically, churn is fairly consistent across most states, with one state standing out with a noticeably higher rate.

![International plan activity and churn by state](images/06_intl_plan_and_map.png)

### Account tenure and payment method
Churn rate drops sharply the longer a customer has been with Databel, especially in the first 20 to 30 months, and month to month contract customers show much more volatile, consistently higher churn across all tenures compared to one and two year contracts. On payment method, direct debit and credit card together make up the large majority of customers, with paper check a small minority.

![Churn rate by account length and payment method](images/07_account_length_payment_method.png)

### Customer service calls
Customers who churned averaged noticeably more customer service calls than those who did not, and this pattern held consistently across states, suggesting call volume is a usable early signal of churn risk.

## Overview dashboard
The final report pulls the key metrics and visuals together into a single summary page, giving a full picture of total customers, churn rate, churn reasons and categories, contract type mix, and churn by state in one view.

![Overview dashboard](images/01_overview_dashboard.png)

## Takeaways

Contract type is the single biggest churn lever in this dataset, with month to month customers churning at many times the rate of yearly contract customers. Competitor activity is the leading stated reason for leaving, senior customers and unlimited data plan holders both carry higher churn risk than expected, and customer service call volume looks like a useful early warning sign. Together these point toward retention efforts that push customers toward longer contracts, address competitor pressure directly, and flag high call volume accounts for proactive outreach.
