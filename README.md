# Cat-XL-Layer-Analysis-YLT-Pipeline
Cat XL Layer Analysis — Catastrophe reinsurance pricing using a 49,999-year stochastic Year Loss Table. Calculates Expected Loss, Attachment &amp; Exhaustion Probability, and regional EL split for two US windstorm excess-of-loss layers via Excel and Python.
Section 1 — Problem statement: given a 49,999-year YLT, price two cat XL layers and produce EL, AP, EP, and regional EL splits.

Section 2 — Methodology (the 5-step pipeline shown above):

Inception filter — IF(DayOfYear ≥ 152, 1, 0)
Event aggregation — SUMIFS by (Year + EventID)
Layer loss formula — MAX(0, MIN(TotalLoss, Exhaustion) − Attachment)
Single shot — MAXIFS per year, IsTrigger flag
Metrics — AVERAGE, COUNTIF, SUMPRODUCT

Section 3 — Results table with EL, AP, EP, Rate on Line for both options.

Section 4 — Regional breakdown with the bar chart showing Florida at 69.3%.
