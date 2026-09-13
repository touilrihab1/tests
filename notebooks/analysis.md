
**Q1:**
The United Kingdom accounts for approximately 88.3% of total revenue lost through returns (€636.9K out of €721.6K), making it by far the largest contributor to revenue leakage.


PAPER CRAFT, LITTLE BIRDIE generated the highest return value (€168.5K) from a single return transaction. This is explained by a full return of 80,995 units only 12 minutes after the original purchase, suggesting a bulk-order cancellation/return rather than typical customer return behavior.
The **REGENCY CAKESTAND 3 TIER** has the highest return frequency, with **359 return transactions**, followed by the **BAKING SET 9 PIECE RETROSPOT** (213) and the **STRAWBERRY CERAMIC TRINKET BOX** (190). This indicates that these products are frequently returned, even though their total financial impact is much lower than the high-value outlier identified in the return-value analysis.

Revenue leakage is highly concentrated in a few months. **December 2011 recorded the highest leakage rate at 28.31%, with €174.1K in returned value against €615.0K in gross revenue.** January 2011 follows with a leakage rate of 13.64%. After these peaks, leakage rates remain substantially lower, with most months below 6.5%. This indicates that certain periods experienced unusually high return activity and may require further investigation for seasonal or operational drivers.

12,340 (69.2%) negative-quantity rows were matched to a prior positive purchase of the same product and customer within the previous month and were classified as True Returns.
5,484 (30.8%) negative-quantity rows could not be matched to a prior purchase within the defined one-month window and were classified as Standalone.
Overall, 17,824 negative-quantity return entries were identified.

**Q2:**

Customer ID 0 was excluded because it represents guest/anonymously recorded transactions rather than an identifiable customer, so it is not suitable for per-customer RFM analysis.


**The results show that the three RFM variables are positively skewed, but to different degrees:
Recency (skewness = 0.89): moderately right-skewed, indicating that most customers have relatively recent purchases, while a smaller number of customers have much higher recency values.
Frequency (skewness = 12.04): highly right-skewed. Most customers have a relatively low number of invoices, while a small number of customers make purchases very frequently.
Monetary (skewness = 25.55): extremely right-skewed, indicating that most customers generate relatively low revenue, while a small number of customers have exceptionally high spending.

**The quantiles confirm this strong concentration. For Monetary, the median is 880.04, meaning that 50% of customers generate revenue below this value. At the 75th percentile, Monetary reaches 2,282.28, while 90% of customers are below 5,490.07. However, the maximum value reaches 603,421.65. This shows that the upper tail contains a small number of extremely high-value customers.

Overall, the distributions are clearly not balanced and contain substantial differences between the majority of customers and a small group of high-frequency or high-value customers. Therefore, quantile-based binning is appropriate because it ranks customers according to their relative position within each distribution rather than relying on fixed numerical intervals.

Selection of the Number of Buckets

We compared 3, 4, and 5 quantile-based buckets for each RFM variable. Recency and Monetary produced relatively balanced customer groups across all three options. Frequency, however, remained highly concentrated in the lower ranges because many customers have a low number of invoices, reflecting the strong right-skewness observed in the distribution.

We selected four buckets as a balance between granularity and interpretability. Three buckets would provide a relatively coarse segmentation, while five buckets would add limited additional business value and would further highlight the concentration of customers in the lowest Frequency group. Four buckets therefore provide sufficient differentiation between customers while keeping the resulting RFM segments practical to interpret.

==>
Champions are the most valuable customers, combining recent purchases, high purchase frequency, and high monetary value. At-risk customers show lower recency despite relatively strong purchasing activity, indicating potential future churn. Low-value or lost customers have both low engagement and low monetary contribution.


- **Q3 — Churn Definition (statistically derived)**

Sensitivity analysis: Increasing the churn cutoff from 106 to 166 days reduced the number of churned customers from 2,847 to 2,464. The baseline cutoff of 136 days resulted in 2,635 churned customers. This shows that the estimated churn population is sensitive to the cutoff choice, although the overall number of churned customers remains within a similar range.

- **Q4 — Cohort Retention**

Cohort retention analysis shows a substantial drop in customer activity after the acquisition month. Retention varies across acquisition cohorts, indicating differences in customer engagement over time. The analysis allows us to identify cohorts with stronger or weaker retention and evaluate how customer activity evolves after acquisition.


- **Q5 — Customer Lifetime Value**

Historical CLV varies substantially across customers, with a small number of customers generating very high cumulative revenue. Customer 18102 has the highest observed CLV at 603,421.65, followed by customer 14646 at 526,751.52. This concentration of revenue highlights the importance of identifying and retaining high-value customers.

