# Hotel Booking Cancellation Analysis

## 1. Project Overview

This project analyzes hotel booking data to identify cancellation patterns, booking behavior, and revenue impact.

## 2. Dataset

* **Dataset:** Hotel Booking Demand
* **Total Records:** 119,390
* **Analysis Focus:** Cancellations, lead time, deposit type, market segment, ADR, and revenue.

## 3. Tools & Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Jupyter Notebook
* LLM

## 4. Part A — Cleaning Rules, Row Counts and Checks

The Hotel Booking Demand dataset was loaded using Pandas from the provided dataset source.

### Data Preparation

The following derived fields and quality flags were created:

* `arrival_date`
* `total_nights`
* `total_guests`
* `flag_zero_guests`
* `flag_missing_country`
* `flag_missing_children`
* `flag_bad_adr`

### Row Counts

| Check                |  Result |
| -------------------- | ------: |
| Total rows           | 119,390 |
| Flagged rows         |   1,829 |
| Clean rows           | 117,561 |
| Row-count validation |    True |

### Validation Checks

The reservation status was cross-checked against `is_canceled`.

| Reservation Status |  Count |
| ------------------ | -----: |
| Canceled           | 43,017 |
| Check-Out          | 75,166 |
| No-Show            |  1,207 |

The arrival date range was validated from **2015-07-01** to **2017-08-31**.

All arrival years were validated against 2015, 2016, and 2017, with the validation result **True**.

## 5. Part B — Key Numbers and Charts

The analysis examined cancellation rates across hotel type, month, lead-time bands, deposit type, and market segment, along with revenue kept and revenue lost.

### Hotel Type

| Hotel        | Cancellation Rate |
| ------------ | ----------------: |
| City Hotel   |            41.73% |
| Resort Hotel |            27.76% |

### Month-wise Cancellation

| Month     | Cancellation Rate |
| --------- | ----------------: |
| April     |            40.80% |
| August    |            37.75% |
| December  |            34.97% |
| February  |            33.42% |
| January   |            30.48% |
| July      |            37.45% |
| June      |            41.46% |
| March     |            32.15% |
| May       |            39.67% |
| November  |            31.23% |
| October   |            38.05% |
| September |            39.17% |

### Lead-time Cancellation

| Lead-time Band | Cancellation Rate |
| -------------- | ----------------: |
| 0-30           |            18.56% |
| 31-90          |            37.70% |
| 91-180         |            44.71% |
| 181-365        |            55.45% |
| 365+           |            67.66% |

### Deposit Type

| Deposit Type | Cancellation Rate |
| ------------ | ----------------: |
| No Deposit   |            28.38% |
| Non Refund   |            99.36% |
| Refundable   |            22.22% |

### Market Segment

| Market Segment | Cancellation Rate |
| -------------- | ----------------: |
| Aviation       |            21.94% |
| Complementary  |            13.06% |
| Corporate      |            18.73% |
| Direct         |            15.34% |
| Groups         |            61.06% |
| Offline TA/TO  |            34.32% |
| Online TA      |            36.72% |
| Undefined      |           100.00% |

### Revenue

| Revenue Type |        Amount |
| ------------ | ------------: |
| Kept         | 25,996,260.41 |
| Lost         | 16,727,237.12 |

### Charts

The notebook includes visualizations for:

* Hotel type cancellation
* Month-wise cancellation
* Lead-time cancellation bands
* Deposit type cancellation
* Market segment cancellation
* Revenue kept versus revenue lost

## 6. Part C — AI-Assisted Analysis

A structured summary table was provided to an LLM to generate a 150-word weekly revenue briefing.

### Initial LLM Briefing

The initial briefing was checked against the summary table for numerical accuracy and unsupported factual claims.

### Verification

| Test               | Correct | Wrong | Invented / Unsupported |
| ------------------ | ------: | ----: | ---------------------: |
| Initial LLM Output |       7 |     0 |                      2 |

### Improved Prompt

The prompt was improved by requiring the LLM to:

* Use only the provided summary table
* Match every number exactly
* Avoid unsupported claims
* Avoid outside knowledge
* Avoid inventing facts or trends
* Use only information supported by the table

### Retest Result

| Test                | Correct | Wrong | Invented / Unsupported |
| ------------------- | ------: | ----: | ---------------------: |
| Improved LLM Output |      10 |     0 |                      0 |

The improved prompt produced a fully verified result with no invented or unsupported claims.

## 7. Key Findings

* **Overall cancellation rate:** 37.04%
* **City Hotel cancellation rate:** 41.73%
* **Resort Hotel cancellation rate:** 27.76%
* **Highest cancellation month:** June — 41.46%
* **Lowest cancellation month:** January — 30.48%
* **Highest lead-time cancellation:** 365+ days — 67.66%
* **Lowest lead-time cancellation:** 0-30 days — 18.56%
* **Non Refund cancellation:** 99.36%
* **Groups cancellation:** 61.06%
* **Online TA cancellation:** 36.72%
* **Corporate cancellation:** 18.73%
* **Revenue kept:** 25,996,260.41
* **Revenue lost:** 16,727,237.12

## 8. Limitations and What I Would Do Next

### Limitations

* The analysis is based on the available hotel booking dataset and summary-level findings.
* The analysis identifies cancellation patterns but does not establish causal relationships.
* The LLM analysis was restricted to the prepared summary table and therefore depends on the quality of that summary.

### What I Would Do Next

* Monitor cancellation patterns regularly using updated booking data.
* Compare cancellation patterns across future booking periods.
* Re-test the AI-assisted briefing when the summary table is updated.
* Continue validating LLM-generated numbers and factual claims against the source analysis.

## 9. How I Used AI Tools

AI tools were used to support the analysis and documentation process.

The main AI-assisted workflow was:

1. A summary table was prepared from the analysis.
2. The summary table was provided to an LLM.
3. The LLM generated an initial weekly revenue briefing.
4. The generated briefing was manually checked against the summary table.
5. Unsupported claims were identified and recorded.
6. The prompt was improved with stricter verification rules.
7. The same summary table was used for a second LLM test.
8. The improved output was verified again.

AI was used for assisted interpretation and prompt testing. The underlying data analysis, calculations, validation, and business findings were performed using the analysis workflow.

## 10. Conclusion

The analysis identifies key cancellation patterns and revenue impact.

The AI-assisted analysis also demonstrates that stricter prompt rules can reduce unsupported claims in LLM-generated business briefings.
