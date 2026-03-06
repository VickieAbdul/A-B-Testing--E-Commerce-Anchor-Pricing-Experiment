# A/B Testing: Anchor Pricing Experiment

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Status](https://img.shields.io/badge/Status-Complete-success)]()
[![Data](https://img.shields.io/badge/Sample-20K%20Visitors-orange)]()

---

## Project Overview

Conducted a statistical A/B test to determine whether displaying anchor pricing (~~$99~~ $79) increases conversion rates and revenue compared to standard pricing ($79) for TechGear Electronics, an e-commerce retailer.

**Business Question:**  
*Does showing the original price crossed out increase customer conversion and revenue?*

**Key Results:**  
- **31% conversion rate increase** (p < 0.001)
- **$7,418 revenue gain** during 14-day test period  
- **99.9% statistical confidence** in results  
- **$180K projected annual revenue impact** with zero implementation cost

---

## Business Impact

### Strategic Value
This A/B test provides TechGear with:
- **Revenue Optimization:** Data-driven pricing strategy
- **Customer Psychology:** Understanding of anchor pricing effectiveness
- **Risk-Free Testing:** Same price for both groups, testing perception only
- **Scalable Implementation:** Zero-cost website text change

### Financial Impact
- **Test Results:** +$7,418 in 14 days
- **Conversion Lift:** 31% increase (2.64% → 3.46%)
- **Annual Projection:** $180,000 additional revenue
- **Implementation Cost:** $0

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

### Results Formula
```
Lift = ((Treatment Rate - Control Rate) / Control Rate) × 100%
```

---

## Project Structure

```
TechGear AB-testing-anchor-pricing/
│
data/
├── techgear_ab_test_data.csv          # Test dataset (20K visitors)
|
analysis/
├── TechGear_analyzedata.ipynb              # Statistical analysis notebook
|
visualizations/
├── chart1_conversion_rate.png         # Conversion rate comparison
├── chart2_conversions.png             # Total conversions
├── chart3_total_revenue.png           # Revenue comparison
├── chart4_revenue_per_visitor.png     # Revenue per visitor
├── chart5_significance.png            # Statistical significance
│
└── README.md                          # Project documentation
```

---

## Key Findings

### Test Results

| Metric | Control (A) | Treatment (B) | Lift |
|--------|-------------|---------------|------|
| **Conversion Rate** | 2.64% | 3.46% | **+31.1%** |
| **Total Conversions** | 264 | 346 | +82 purchases |
| **Total Revenue** | $22,176 | $29,594 | **+$7,418** |
| **Revenue/Visitor** | $2.22 | $2.96 | **+33.5%** |

### Statistical Validation
- **Chi-Square Statistic:** χ² = 11.09
- **P-value:** 0.0009 (highly significant)
- **Confidence Level:** 99.9%
- **95% Confidence Intervals:** Non-overlapping (strong evidence)

### Business Interpretation
The anchor pricing treatment shows statistically significant improvement across all key metrics. The p-value of 0.0009 indicates less than 0.1% probability that results are due to random chance.

---

## Business Recommendations

### Primary Recommendation
** IMPLEMENT ANCHOR PRICING (Treatment B)**

**Rationale:**
- Statistically significant 31% conversion rate increase
- 99.9% confidence in results
- Zero implementation cost (simple text change)
- Easily reversible if needed

### Projected Annual Impact

**Assumptions:**
- 100,000 monthly website visitors
- Current conversion rate: 2.64%
- Treatment conversion rate: 3.46%

**Calculations:**
- Current monthly conversions: 2,640
- Projected monthly conversions: 3,460
- Additional conversions: 820/month
- Monthly revenue increase: ~$15,000
- **Annual revenue increase: $180,000**

### Implementation Plan
1. **Immediate:** Update product page pricing display
2. **Week 1-4:** Monitor actual conversion rates vs forecast
3. **Month 2:** Analyze by traffic source and device
4. **Month 3:** Expand to other product categories
5. **Ongoing:** A/A testing to validate tracking accuracy

### Next Steps
- Test different discount percentages (10%, 30%, 50%)
- Segment analysis by customer type (new vs returning)
- Test time-limited offers ("Today only!")
- Measure long-term customer lifetime value impact

---

## Technical Details

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

### Data Generation
- **Simulation Period:** 14 days
- **Conversion Rates:** 3.0% (control) vs 3.5% (treatment)
- **Random Noise:** ±10% variation for realism
- **Revenue Calculation:** quantity × $79

### Statistical Methods
**Chi-Square Test:**
```python
from scipy.stats import chi2_contingency
chi2, p_value, dof, expected = chi2_contingency(contingency_table)
```

**Confidence Intervals:**
```python
z = 1.96  # 95% confidence
se = sqrt((p * (1 - p)) / n)
ci = (p - z*se, p + z*se)
```

---

## Skills Demonstrated

### Technical Skills
- **A/B Testing:** Experimental design and execution
- **Statistical Analysis:** Chi-square tests, hypothesis testing, p-values
- **Python Programming:** pandas, scipy, matplotlib, seaborn
- **Google Colab:** Cloud-based analysis environment
- **Data Visualization:** Clear, business-focused charts

### Business Skills
- **Experimental Design:** Controlled randomized testing
- **Revenue Impact Analysis:** Converting statistics to dollar impact
- **Strategic Recommendations:** Data-driven decision making
- **Stakeholder Communication:** Translating technical results for business audiences

---

## Future Enhancements

Potential improvements for this analysis:

1. **Segmentation Analysis:** Break down results by device, traffic source, customer type
2. **Long-term Monitoring:** Track conversion rates for 30-90 days post-launch
3. **Multivariate Testing:** Test multiple changes simultaneously
4. **Customer Lifetime Value:** Measure long-term revenue impact
5. **Competitive Analysis:** Compare anchor pricing across product categories

---

## 📫 About This Project

This project was completed as part of my data analytics portfolio to demonstrate:
- Statistical hypothesis testing skills
- A/B testing methodology and best practices
- Python data analysis capabilities
- Business impact analysis and ROI calculation
- Clear communication of technical insights

The dataset is simulated but follows realistic e-commerce patterns and industry-standard A/B testing practices.

---

## Author

**Victoria Abdul**  
Data Analyst | Python | Statistical Analysis

- Email: your.email@example.com
- LinkedIn: [linkedin.com/in/victoria-abdul](https://linkedin.com/in/victoria-abdul)
- GitHub: [github.com/vickieabdul](https://github.com/vickieabdul)

---

## License

MIT License - Free to use for educational and portfolio purposes.

---

**⭐ Star this repository if you found this analysis helpful!**

---

*Last Updated: March 2026*
