# A/B Testing: Anchor Pricing Experiment

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Status](https://img.shields.io/badge/Status-Complete-success)]()
[![Data](https://img.shields.io/badge/Sample-20K%20Visitors-orange)]()

---

## Project Overview

This project tests whether showing anchor pricing, displaying a product as "$99 now $79" rather than just "$79", increases conversion rates and revenue for TechGear Electronics on their wireless headphones product.
The question behind the experiment is a common one in e-commerce pricing strategy: does giving customers a reference point for what something used to cost change their decision to buy? The answer has direct implications for how TechGear prices products across its entire catalogue.

**Business Question:**  
Does anchor pricing increase sales enough to justify rolling it out as TechGear's default pricing display strategy?

## Dataset Description
The experiment ran for 14 days in January 2025 and captured:
- 20,000 website visitors split evenly across control and treatment groups
- Conversion status per visitor (purchased or not)
- Quantity purchased per converting visitor
- Revenue generated per group at a product price of $79

---

Tools Used

Python (Pandas, NumPy, Matplotlib, Seaborn, SciPy)

---

## Methodology

### A/B Test Design
**Test Setup:**
- **Control Group (A):** Display "$79" only
- **Treatment Group (B):** Display "~~$99~~ $79" (anchor pricing)
- **Sample Size:** 20,000 visitors (10,000 per group)
- **Duration:** 14 days
- **Randomization:** 50/50 traffic split

### Statistical Analysis
**Chi-Square Test for Conversion Rate:**
- Null Hypothesis (H₀): No difference in conversion rates
- Alternative Hypothesis (H₁): Conversion rates differ
- Significance Level: α = 0.05

**Key Metrics Analyzed:**
1. Conversion Rate (% who purchased)
2. Total Revenue (quantity × price)
3. Revenue Per Visitor (average revenue per visitor)

---

## Analysis Structure
1. Group Setup and Data Validation
Split 20,000 visitors into two equal groups of 10,000. Control group saw standard pricing ($79). Treatment group saw anchor pricing ($99 now $79). Verified the split was clean and the test period was consistent across both groups.
2. Conversion and Revenue Metrics
Calculated conversion rate, total conversions, total revenue, and revenue per visitor for both groups to establish the baseline performance gap between the two pricing approaches.
3. Statistical Significance Testing
Ran a chi-square test on the conversion outcomes to determine whether the difference between groups was statistically real or could have occurred by chance. A result is only actionable if the probability of it being a fluke is below 5%.
4. Business Impact Projection
Translated the test results into projected annual revenue impact based on realistic monthly visitor assumptions to give leadership a concrete number to evaluate.

---

## Key Findings

### Test Results

| Metric | Control (A) | Treatment (B) | Lift |
|--------|-------------|---------------|------|
| **Conversion Rate** | 2.64% | 3.46% | **+31.1%** |
| **Total Conversions** | 264 | 346 | +82 purchases |
| **Total Revenue** | $22,176 | $29,594 | **+$7,418** |
| **Revenue/Visitor** | $2.22 | $2.96 | **+33.5%** |

---

### Statistical Validation
- **Chi-Square Statistic:** χ² = 11.09
- **P-value:** 0.0009 (highly significant)
- **Confidence Level:** 99.9%
- **95% Confidence Intervals:** Non-overlapping (strong evidence)

---

### Business Interpretation
The anchor pricing treatment shows statistically significant improvement across all key metrics. The p-value of 0.0009 indicates less than 0.1% probability that results are due to random chance.

---

## Key Insights

- Anchor pricing increased the conversion rate from 2.64% in the control group to 3.46% in the treatment group, a 31.1% lift in conversions.
- Revenue per visitor increased from $2.54 to $3.51, a 37.9% improvement, meaning anchor pricing not only converted more visitors but also generated more revenue from each one.
- The result is highly statistically significant with a p-value of 0.0009. There is less than a 0.1% chance this difference is due to random variation. The finding is real.
- Over the 14-day test window the treatment group generated $35,076 versus $25,438 for the control group, a difference of $9,638 on 10,000 visitors each.
- Projected across 100,000 monthly visitors at an average order value of $85, implementing anchor pricing is worth an estimated $836,400 in additional annual revenue at zero implementation cost.

---

## Recommendations
- Roll out anchor pricing as the default display strategy. The statistical evidence is strong, the revenue uplift is material, and the cost of implementation is zero. There is no meaningful downside in this data.
- The 31.1% conversion lift is not a marginal result. It is the kind of number that compounds quickly at scale. At 100,000 monthly visitors that is an additional 820 purchases per month that the business is currently leaving on the table by showing a flat price.
- Before full rollout, consider testing anchor pricing across other product categories to confirm the effect is not specific to wireless headphones. The psychological mechanism behind anchor pricing, giving customers a reference point, should work broadly, but validating it on two or three other products before making it catalogue-wide is good practice.
- Monitor conversion rates monthly after rollout. If the lift shrinks over time it may indicate that customers are becoming familiar with the anchor and discounting it. Refreshing the reference price periodically can help sustain the effect.

---

## Executive Conclusion
The experiment has a clear answer: anchor pricing works for TechGear. A 31.1% conversion lift, a p-value of 0.0009, and a projected $836,400 annual revenue increase with no implementation cost make this one of the highest return decisions the business can make right now. The recommendation is to implement immediately and monitor for sustainability.

---

### Dataset Schema

| Column | Type | Description |
|--------|------|-------------|
| visitor_id | int | Unique visitor identifier (1-20,000) |
| test_group | string | A_Control or B_Treatment |
| variant | string | Just_Price or Anchor_Price |
| price_shown | string | "$79" or "~~$99~~ $79" |
| visit_date | date | Visit date (2025-01-01 to 2025-01-14) |
| converted | int | 1 if purchased, 0 otherwise |
| quantity | int | Items purchased (0-3) |
| traffic_source | string | organic_search, paid_ads, social_media, direct, email |
| device | string | desktop, mobile, tablet |
| time_on_page | float | Time on page (seconds) |
| visitor_type | string | new or returning |

---

## Future Enhancements

Potential improvements for this analysis:

- Test different discount percentages (10%, 30%, 50%)
- Segment analysis by customer type (new vs returning)
- Test time-limited offers ("Today only!")
- Measure long-term customer lifetime value impact

---


The dataset is simulated but follows realistic e-commerce patterns and industry-standard A/B testing practices.

---

## Author

**Victoria Abdul**  
Data Analyst | Python | Statistical Analysis

- Email: victoria.j.abdulkadir@gmail.com
- LinkedIn: [linkedin.com/in/victoria-abdul](https://www.linkedin.com/in/victoriajabdul/)
- GitHub: [github.com/vickieabdul](https://github.com/vickieabdul)

---

## License

MIT License - Free to use for educational and portfolio purposes.

---

**⭐ Star this repository if you found this analysis helpful!**

---

*Last Updated: March 2026*
