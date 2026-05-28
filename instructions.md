## Track B — Micro-Business Loan Default

### The Story

**ClearCredit** is a microfinance institution that provides small business
loans (€500–€8 000) to independent workers and micro-entrepreneurs across
several European regions.  Their loan officers used to make credit decisions
manually, but the volume of applications has grown too large for that approach.

The risk team has assembled two years of historical loan data, labelled with
the final repayment outcome.  Your task is to build an automated credit
scoring model that can flag high-risk applications at submission time, so
that a human reviewer can intervene before the loan is issued.

Getting this right has real asymmetric stakes: approving a bad loan costs the
institution money; rejecting a good loan costs a small business owner an
opportunity they may not recover easily.

### Dataset Files

| File | Rows | Columns | Target |
|---|---|---|---|
| `track_b_loan_default_train.csv` | 1200 | 14 | `default` |
| `track_b_loan_default_test.csv` | 300 | 14 | `default` |

**Class balance:** approximately 18 % of loans in the training set are labelled
`default = 1`.

### Feature Reference

| Feature | Type | Range | Description |
|---|---|---|---|
| `applicant_age` | int | 22–65 | Age of the applicant at application time. |
| `monthly_income_eur` | float | 800–6000 | Self-declared gross monthly income. |
| `loan_amount_eur` | float | 500–8000 | Requested loan amount. |
| `debt_to_income_ratio` | float | 0–3 | Approximate ratio of loan amount to monthly income, measured with noise. |
| `employment_stability_score` | float | 0–10 | Composite employment stability score (higher = more stable). |
| `prior_defaults_count` | int | 0–3 | Number of prior defaults in the credit bureau. |
| `credit_bureau_score` | float | 300–850 | Standard credit score from the national bureau. |
| `sector_risk_index` | int | 1–5 | Industry risk level (1 = low, 5 = high). |
| `regional_unemployment_pct` | float | 3–18 | Local unemployment rate in the applicant's region (%). |
| `savings_eur` | float | 0–5000 | Declared available savings / liquidity buffer. |
| `num_active_credit_lines` | int | 0–5 | Number of other currently active credit accounts. |
| `declared_address_match` | binary | 0/1 | Whether declared address matches the bureau address. |
| `application_quarter` | int | 1–4 | Quarter of application submission. |
| **`default`** | binary | 0/1 | **Target: 1 = defaulted within loan term.** |

---