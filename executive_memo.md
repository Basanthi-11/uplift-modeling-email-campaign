
EXECUTIVE MEMO
==============
TO: Marketing & Growth Leadership
FROM: Data Science Team
RE: Email Campaign Uplift Analysis — Hillstrom Dataset
DATE: June 2026

EXECUTIVE SUMMARY
-----------------
Standard response models identify customers likely to convert.
Uplift models identify customers who convert BECAUSE of our intervention.
This distinction has significant implications for campaign ROI.

KEY FINDINGS
------------
1. SLEEPING DOGS (Critical Risk)
   - 504 customers (1.2% of base) are actively harmed by email
   - Without email: 57.6% visit rate
   - With email: 15.4% visit rate
   - Recommendation: Permanently suppress these customers from campaigns

2. BUDGET-CONSTRAINED TARGETING
   - With 5,000 email budget:
   - Random targeting: 196 incremental visits
   - Uplift model targeting: 640 incremental visits
   - Improvement: +226% incremental visits vs random

3. MODEL PERFORMANCE
   - T-Learner Uplift Model Qini: 1,263
   - Baseline Response Model Qini: 994
   - Uplift model beats baseline by 27.1%
   - Uplift model beats random by 54.2%

RECOMMENDATION
--------------
Deploy uplift model for all future email campaigns with three rules:
1. Suppress sleeping dogs permanently (504 customers identified)
2. Target persuadables first (positive uplift score > 0.05)
3. Re-evaluate uplift scores quarterly as customer behavior evolves

METHODOLOGY
-----------
- Dataset: 64,000 customers, 3-arm experiment (Mens Email, Womens Email, Control)
- Model: T-Learner with Gradient Boosting (separate treatment/control models)
- Evaluation: Qini curve and coefficient
- Validation: Holdout test set with 80/20 split

NEXT STEPS
----------
1. A/B test uplift model targeting vs current baseline in production
2. Build S-Learner and X-Learner variants for comparison
3. Extend analysis to Womens Email segment
4. Implement real-time scoring pipeline for campaign automation
