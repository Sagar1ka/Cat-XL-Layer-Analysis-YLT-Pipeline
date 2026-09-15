# Insurance : Cat XoL-Layer-Analysis-YLT-Pipeline - Hypothetical Data
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


•  Using the Year Loss Table, I have calculated the expected loss, AP and EP for the following two catastrophe excess of loss layers: <br>
1.  Option 1 (O1): $100m xs $140m, single shot, United States windstorm, inception June 1st to year end <br>
2.  Option 2 (O2): $70m xs $95m, single shot, Florida windstorm only, inception June 1st to year end <br>

LAYER SUMMARY
  1. Simulation: 49,999 annual simulations drawn from the YLT. <br>
  2. Inception filter: Only events with DayOfYear ≥ 152 (June 1) are included in-scope. <br>
  3. Single Shot: Layer triggered at most once per year by the largest qualifying event (no reinstatements). <br>
  4. Layer Loss per event = MAX(0, MIN(TotalEventLoss, Exhaustion) − Attachment). <br>
  5. Option 1 aggregates all US states; Option 2 is restricted to Florida-only losses. <br>
  6. EL = average annual layer loss across all 49,999 years.  <br>
  7. AP = proportion of years where max event loss ≥ Attachment. <br>
  8. EP = proportion of years where max event loss ≥ Exhaustion Point. <br>
