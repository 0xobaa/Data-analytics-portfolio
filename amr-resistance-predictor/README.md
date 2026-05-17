## AMR Resistance Predictor & Trend Forecasting

Two notebooks. One predicts whether a patient's isolate will 
be carbapenem-resistant. The other forecasts quarterly resistance 
rates per facility.

Both use the AMR Watch Nigeria synthetic dataset: 30,000 isolates 
from 12 Nigerian teaching hospitals spanning 2023-2025.

---

### Part 1 — Resistance Prediction

The problem: given a patient's demographics, specimen type, 
organism, and ESBL status, can you flag likely carbapenem 
resistance before the result is confirmed?

Tested five approaches. Short answer: Logistic Regression won. 
which wasn't the expected result going in.

| Model | Recall | Accuracy |
|---|---|---|
| Logistic Regression | 59% (80% at 0.4 threshold) | 64% |
| XGBoost | 49% | 65% |
| Random Forest | 28% | 71% |
| Neural Network + SMOTE | 26% | 76% |

The accuracy numbers may be misleading here. A model that flags 
nothing as resistant gets 74% accuracy by doing nothing useful. 
Recall on the resistant class is the number that matters for 
surveillance, as we don't want to miss resistant cases. Therefore,
we prioritized few false negatives (Higher recall but with a 
caveat of lower precision)

At the default 0.5 threshold, Logistic Regression catches 59% 
of resistant isolates. Drop the threshold to 0.4 and that 
jumps to 80%, at the cost of more false positives (lower precision). For a 
screening tool in a setting where missing a carbapenem-resistant 
case means a patient gets the wrong antibiotic, that trade-off 
Makes sense.

**What this model can't do:** it can't replace culture results or guide 
individual treatment decisions. It works as a risk stratification 
tool while results are pending.


**The real problem:** phenotypic features only. Without MIC 
values, resistance genes, or prior antibiotic exposure data, 
65-70% recall is roughly where this approach tops out. That's 
a data problem, not a model problem.

---

### Part 2 — Quarterly Trend Forecasting

Takes quarterly resistance rates per facility per antibiotic 
and projects forward. Built on 12 quarters of LUTH Lagos 
Meropenem data as the test case; minimum 219 isolates per 
quarter throughout.

Three models, three different answers:

| Model | 2026Q1 | 2026Q2 |
|---|---|---|
| Linear Regression | 27.3% | 27.3% |
| ARIMA (1,1,1) | 29.7% | 28.6% |
| Prophet (3 changepoints) | 33.8% | 33.8% |

ARIMA feels most honest for 12 quarters. It responds to recent 
data without trying to learn seasonal patterns, it doesn't have 
enough history to confirm. Prophet works well but needs 20+ 
quarters before its seasonality detection stops overfitting 
on single-quarter spikes.

The notebook also includes automated anomaly detection: flags 
quarters where resistance jumped more than 1.5 standard 
deviations above baseline. 2023Q3 came up as the only true 
anomaly in LUTH's Meropenem data. Whether that reflects a 
real outbreak or noise in a single quarter might be a question for 
the infection control team.

---

### Why these antibiotics

Priority panel built from NCDC NAP 2.0 (2024-2028), the 
Nigeria EML 7th Edition, and published point-prevalence 
surveys across Nigerian tertiary hospitals. Meropenem leads 
because it's the last reliable carbapenem in most Nigerian 
ICU formularies and the one where rising resistance has the 
fewest fallback options.



### For AMR Watch
We'll only provide  facility resistance trend prediction during 
the pilot months such as: "Meropenem resistance is predicted to 
increase by 10% In the next quarter, prescribe carefully." 
When we have richer data that spans across different facilities 
and years, which covers patient exposure, resistant genes, and
MIC, we'll introduce patient resistance prediction

---

### Context

This is the analytical layer behind AMR Watch Nigeria, a 
surveillance dashboard aggregating resistance data from 
Nigerian health facilities. The dashboard is live. These 
notebooks document the prediction methodology that will 
back the platform's ML features as real facility data 
accumulates.
