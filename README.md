# Lending Club Credit Modeling & Portfolio Optimization

Welcome to my Project! 

This is a deep dive into Lending Club's data to uncover patterns, challenges, and opportunities that can inform future decision-making. As a sophomore majoring in Business Analytics and Finance, I developed this project to apply my curiosity in a real-world setting, bridging analytical thinking with business impact.

This analysis uses LendingClub loan-level data publicly available on Kaggle ([wordsforthewise, 2021](https://www.kaggle.com/datasets/wordsforthewise/lending-club)).

## TABLE OF CONTENTS
* [Project Overview](#project-overview)
* [Project Objectives](#project-objectives)
* [Portfolio Analysis](#portfolio-analysis)
* [Models & Evaluations](#models--evaluations)

##  PROJECT OVERVIEW
Lending Club (LC), a pioneer in peer-to-peer lending, revolutionized consumer credit by enabling retail and institutional investors to fund personal loans directly. 

While this innovation unlocked new growth opportunities, it also introduced significant risk exposure due to borrower quality variance, macroeconomic sensitivity, and underwriting scalability.

This project combines Lending Club’s business-focused analysis with predictive modeling to explore how approval decisions, borrower traits, and risk factors interact over time. 

The dataset includes both approved and rejected loans issued between 2007 and 2018, offering a comprehensive view of Lending Club’s lending strategy over more than a decade.

## PROJECT OBJECTIVES
* Investigate the drivers of portfolio losses and surface high-risk borrower segments
* Flag early warning signals to support proactive risk mitigation
* Evaluate risk-adjusted profitability across borrower segments to inform pricing and approval strategy
* Develop a Loan Approval Pre-screener model to simulate loan acceptance decisions and evaluate trade-offs between approval volume and portfolio risk
* Develop a Loan Charge-off Risk Model focused on precision, used to flag high-charge-off borrowers at origination

## PORTFOLIO ANALYSIS 
### [View notebook](Lending_Club_Loan_Portfolio_Analysis.ipynb)

This portfolio analysis traces Lending Club’s journey through its startup, hypergrowth, crisis, and early recovery by examining loan issuance, charge-offs, borrower quality, and risk segmentation over time (2007-2018)

### 1.	Loan Issuance & Charge-Off Trends

<p align="center">
  <img src="Visuals/Loan%20Issuance%20%26%20Charge-Off%20Trends.png" width="1000">
</p>

* **Early stage (2007–2011)**
  * Issuance climbed moderately; Charge-offs remained low
* **Hypergrowth (2012–2015)**
  * Issuance skyrocketed as LC aggressively lowered underwriting standards to scale
  * The successful IPO in 2014 injected cash and pressured management to sustain high growth rates ([Wikipedia, n.d.-a](https://en.wikipedia.org/wiki/LendingClub#:~:text=In%20March%202014%2C%20LendingClub%20began,37))
  * This growth came at a cost: charge-offs increased dramatically, signaling deteriorating credit quality as LC prioritized expansion over prudent lending
* **Crisis hit in 2016 - Freeze in 2017**
  * Internal loan misreporting scandal led to the CEO’s resignation and eroded investor confidence ([Wikipedia, n.d.-b](https://en.wikipedia.org/wiki/LendingClub#:~:text=In%20April%202016%2C%20a%20LendingClub,46))
  * Investor withdrawals froze issuance, while LC implemented tighter governance, more stringent underwriting, and a focus on higher-quality borrowers to rebuild investor trust
  * As a result, loan issuance stagnated but charge-offs began to fall sharply
*	**Recover in 2018**
  * Issuance rebounded modestly, and charge-offs fell to their lowest levels in years, reflecting a reset toward sustainable growth and credit discipline

### 2.	Borrower Demand, Approval Rates & Credit Quality Evolution

<p align="center">
  <img src="Visuals/Borrower%20Demand,%20Approval%20Rates%20%26%20Credit%20Quality%20Evolution.png" width="1000">
</p>

* **Early stage (2007–2011)**
  * Approval rates and borrower demand grew gradually
  * Borrower credit quality (as measured by average FICO scores) peaked, LC attracted prime borrowers wary of banks after the financial crisis
* **Hypergrowth (2012–2015)**
  * LC raised approval rates by loosening credit filters, which allowed more subprime borrowers onto the platform
  * FICO scores dropped to their lowest point while charge-offs soared — a direct consequence of chasing volume at the expense of borrower quality
*	**After 2016**
  * Approval rates declined sharply as risk thresholds rose, filtering out weaker applicants
  * Borrower credit quality (FICO scores) rose again, and investors returned as trust in LC’s governance and underwriting improved

### 3.	Risk Segment Dynamics

<p align="center">
  <img src="Visuals/Risk%20Segment%20Dynamics.png" width="1000">
</p>

* **Early stage (2007–2011)**
  * LC’s portfolio was dominated by Grade A and B loans, catering to prime borrowers and minimizing charge-offs
* **Hypergrowth (2012–2015)**
  * LC shifted aggressively into riskier D, E, F, and G grades, which offered higher yields to investors but carried much greater charge-off risk
  * This shift coincided with a drop in FICO scores, higher charge-offs, and ballooning issuance
*	**After 2016**
  * Issuance of F and G grades nearly disappeared, while safer A and B grades regained prominence
  * Despite the pullback from high-risk loans, investors remained engaged because riskier loans in earlier years offered commensurately higher interest rates, partially compensating for higher charge-offs.

### Summary:
From 2007 to 2018, Lending Club evolved from a cautious startup into a hypergrowth leader, then faced a crisis that forced a reset. After years of aggressive expansion and rising charge-offs, the 2016 scandal marked a turning point. By tightening standards and improving portfolio quality, the company stabilized loan performance and regained momentum, closing the decade stronger and more disciplined.

## MODELS & EVALUATIONS

To complement the portfolio analysis with actionable decision tools, I developed two predictive models designed to help Lending Club intelligently navigate the trade-offs between growth, risk, and profitability.

### 1.	Loan Approval Model - [View notebook](Lending_Club_Loan_Approval_Model.ipynb)

<p align="center">
  <img src="Visuals/Loan%20Approval%20Model.png" width="1000">
</p>

* Model: Logistic Regression
*	Serves as a pre-screener to expand borrower approvals while safeguarding portfolio health
*	Quantifies how much risk is added at each approval threshold, enabling Lending Club to adjust its growth appetite while keeping charge-offs in check
*	Key insight: Raising approval thresholds too aggressively shrinks opportunities far more than it reduces risk, highlighting the cost of being overly cautious
*	Performance: AUC ≈ 0.86

### 2.	Loan Charge-Off Prediction Model - [View notebook](Lending_Club_Loan_Charge_Off_Prediction_Model.ipynb)

<p align="center">
  <img src="Visuals/Loan%20Charge-Off%20Prediction%20Model.png" width="1000">
</p>

* Model: XGBoost
*	Protects the portfolio’s bottom line by identifying borrowers most likely to charge off at origination
*	Performance: AUC ≈ 0.72
*	Feature importance analysis: Revealed the key drivers of charge-off risk: high interest rates, elevated debt-to-income ratios, low credit scores, and heavy revolving credit utilization

## CONTACT
This project was more than understanding Lending Club’s story or analyzing their data - It was an opportunity for me to challenge myself to conduct thoughtful analysis and design meaningful solutions aligned with their strategic goals. It reflects what I value most: staying curious, learning deeply, and turning insights into impact.

For any questions, suggestions, or discussion, feel free to reach out:

* Email: nhatlinh12150@gmail.com
* LinkedIn: [Nhat-Linh Tran](https://www.linkedin.com/in/nhat-linh-tran/)
  
Thank you for visiting my project - I hope you find it interesting and informative!
