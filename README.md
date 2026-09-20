# Insurance : Cat XoL-Layer-Analysis-YLT-Pipeline - Hypothetical Data

Developed a Cat XL pricing tool (Python + Excel) processing 49,999 stochastic loss scenarios to calculate EL, AP, EP, and regional loss attribution for two US windstorm reinsurance layers (ILS cover), with automated Excel report generation via openpyxl <br>

Cat XL Layer Analysis — Catastrophe reinsurance pricing using a 49,999-year stochastic Year Loss Table. Calculates Expected Loss, Attachment &; Exhaustion Probability, and regional EL split for two US windstorm excess-of-loss layers via Excel and Python. <Br>

Problem statement: given a 49,999-year YLT, price two cat XL layers and produce EL, AP, EP, and regional EL splits. <br>
Inception filter:   June 1st to year end
Event aggregation — SUMIFS by (Year + EventID)
Layer loss formula — MAX(0, MIN(TotalLoss, Exhaustion) − Attachment)
Single shot — MAXIFS per year, IsTrigger flag
Metrics — AVERAGE, COUNTIF, SUMPRODUCT

•  Using the Year Loss Table, I have calculated the expected loss, AP and EP for the following two catastrophe excess of loss layers: <br>
1.  Option 1 (O1): $100m xs $140m, single shot, United States windstorm, inception June 1st to year end <br>
2.  Option 2 (O2): $70m xs $95m, single shot, Florida windstorm only, inception June 1st to year end <br>

