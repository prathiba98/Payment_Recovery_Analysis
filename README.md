# PAYMENT FAILURE AND REVENUE RECOVERY ANALYSIS

## Project Overview

This project analyzes payment failures and retry behavior to understand revenue recovery opportunities and permanent revenue loss using only Python.

The goal is to identify:

1.Why payments fail?

2.How retry attempts impact recovery?

3.How much revenue is recovered vs lost?

4.What actions can reduce revenue leakage?

This is an end-to-end analytics project covering data generation, cleaning, analysis, and business recommendations.


## Problem Statement

Payment failures directly impact revenue and user experience.
Not all failures are equal — some can be recovered through retries, while others lead to permanent loss.

This project answers:

1.Which failure reasons cause the most loss?

2.How effective are retry attempts?

3.How much revenue can be recovered?

4.Where should businesses focus recovery efforts?

## Tools used

Python 
- Pandas
- numpy
- matplotlib
- plotly

## Key Analysis Performed

step 1:

Data generation 

a. Generated realistic synthetic payment transaction data using pandas,numpy(np.random.choice).

step 2:

Data Cleaning and Feature Engineering

a.Handled missing values and data types.

b.Created business-ready features:

-retry_buckets

-recovery_status

-revenue_recovered & revenue_lost

step 3:

Payment Failure Analysis

a. Overall failure rate was calculated.

b. Calculated Failure rate by:

-payment method

-device

-failure reason

and created visuals of the same using matplotlib.

<img width="576" height="455" alt="Image" src="https://github.com/user-attachments/assets/28abfecb-b804-4582-aaf3-fcf04ae79c1f" />



<img width="563" height="496" alt="Image" src="https://github.com/user-attachments/assets/c3211d88-cd21-4b9c-8a7b-abc26848e3c7" />


<img width="489" height="389" alt="Image" src="https://github.com/user-attachments/assets/7eff4ec6-33e6-4475-8401-2d20fcf582fc" />


step 4:

Retry and Recovery Analysis

a.Retry behavior after payment failure was calculated and a bar plot was constructed (plt.bar()).

b.Recovery rate by retry count was calculated and a line plot of same plotted.

c.Identification of retry behaviour.

<img width="562" height="455" alt="Image" src="https://github.com/user-attachments/assets/8b776f2b-b46f-43be-aad3-903df252cf41" />


<img width="580" height="455" alt="Image" src="https://github.com/user-attachments/assets/8b325bb7-d9b3-480f-9ca3-434c8287e544" />


step 5:

Revenue Impact Analysis

a. Overall Revenue Metrix like total revenue attempted,total revenue lost and total revenue recovered were calculated.

b.Revenue distribution by payment outcome was calculated and a bar graph was plotted.

c.Revenue loss by failure reason
was calculated and represented it using a line plot.

d.Revenue recovered by payment method was found and a funnel chart was created using plotly library.

e.A Pareto insight of revenue loss concentration was studied.


<img width="571" height="514" alt="Image" src="https://github.com/user-attachments/assets/291577f0-cc59-4fc5-9038-cc57fad14b16" />


<img width="828" height="525" alt="Image" src="https://github.com/user-attachments/assets/be13f3eb-7ceb-4cf2-b9f4-40b089de47a4" />



<img width="554" height="455" alt="Image" src="https://github.com/user-attachments/assets/68616ec4-d140-4d91-9fa9-be17c785f604" />


step 6:

Buisness Insights and Recommendations.

Insight 1:

Most failed transactions are driven by a small set of failure reasons such as network errors and timeouts, indicating operational issues rather than customer intent.

Insight 2:

A large share of failed payments are successfully recovered through retries, especially within the first one or two attempts.

Insight 3:

Retry behavior helps recover a substantial portion of revenue that would otherwise be permanently lost.

Insight 4:

Failures caused by insufficient funds show low recovery, contributing disproportionately to revenue loss.

Recommendation 1:

a. Smarter retry strategy.

b.Increase retries for network and timeout failures.

c.Reduce retries for insufficient funds.

d.Introduce delayed retries instead of immediate repeats.

Recommendation 2:

a.Revenue-focused recovery.

b.Prioritize retry flows for high-value transactions.

c.Flag repeated failures on large amounts.

Recommendation 3:

a.Payment method optimization.

b.Improve reliability of high-failure payment methods.

c.Promote payment methods with higher recovery success.
 

 
 
