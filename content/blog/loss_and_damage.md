---
title: "Loss & Damage Fund"
date: 2024-04-18T02:01:58+05:30
description: "--"


tags: [R, RShiny, Equity]
---

![Future Energy](https://colinpaulish.github.io/cp_hugo_nz30/img/loss_and_damage.png "negotiating for equity")

## The [WIP] Loss and Damage Tool
Check out what I built to add some data to this conceptually fascinating topic:
[R Shiny Loss & Damage Tool](https://colinpaulish.shinyapps.io/loss_and_damages/)


## Overview
General consensus coming out of COP27 was disappointment. Commitments once again exceeded action and many climate enthusiasts left with more questions than answers. An exciting development that did come out of COP27 was the agreement of a ‘Loss and Damage’ fund. In principle, this agreement formalizes mostly rich countries' acknowledgement that there is a need for financial assistance to developing nations facing the brunt of the effects of climate change. **As with the rest of the conference, fundamental operational questions were left unanswered such as – who pays who, through what finance vehicle, at what amount over what time period?**

The lack of clarity scares me – until there are answers, progress will be slow and any progress that is made will almost assuredly be at  a smaller scale than needed. It is a messy and complicated topic with no right answers to the questions above - factors that drew me to this topic.  In this particular post, I will attempt to put in place a beginning funding “formula” using public data. Before doing so, I’ll explain why this is so important and conclude by scratching the surface of considerations that extend beyond the flow of financing.

## Motivation
The reason this fund is so important is both simple and alarming:

* Cumulative CO2 and its equivalent emissions are incredibly lopsided with the EU, USA, and China representing ~60% of global cumulative emissions. Comparatively, South America and Africa represent just 6% of the total [source](https://ourworldindata.org/contributed-most-global-co2).


* The effects of global warming are also not distributed equally. Generally, places near the equator are more at risk which tend to skew less developed and more vulnerable. This is shown at a high-level below where the darker shades represent greater risk and tend be closer to the equator in developing nations.
![Cumulative CO2](https://colinpaulish.github.io/cp_hugo_nz30/img/inform_risk.png "risk score")



Each of these on their own is powerful. Taken together, it screams unfairness. Generally, the countries and communities who have done the least to raise our global temperature (and dirty our air) are bearing the biggest costs.  The numbers are hard to contextualize. Just before COP27, a group of 55 developing countries added up their climate linked losses and valued it at $525 or 20% of their collective GDP [source](https://climatedata.imf.org/datasets/7cae02f84ed547fbbd6210d90da19879_0/about). Unfortunately, we are entering a new “normal” – one that will have more catastrophic events at increasing scale. Until we are carbon negative, tomorrow will have more carbon than today.



## The Methodolodgy

#### Goals
Put simply, **this is a first attempt to put some rigor and systems around funding**. This serves a starting point – for the inputs, data sources, designations, formulas, etc. As with my other posts, I have simplified the “equation” while trying to keep the nature of the agreement and the moral side intact. Countries that have contributed and are more financially secure should pay more. Countries that are bearing more of the costs should receive more.

As mentioned above, I have also developed an R Shiny tool to play around with some of the inputs that you can find here.


#### Who is paying vs who is receiving?
A common theme, **it is not clear who will be funding vs paying**. The deal says the fund will assist, “developing countries that are particularly vulnerable to the adverse effects of climate change.” Defining the funders was impressively even more vague mentioning developed countries and “other private and public sources.”

The World Economic Situation Prospects (WESP) categorizes countries into three broad categories: developed economies, economies in transition, and developing economies (source).  The UN categorizes the Least Developed Countries, of which there are currently 46 (source). Plenty of other categorizations could similarly be used - such as an economies per capita gross national income (GNI). Put simply there is no “right” way to completely fairly categorize who should fund and who should receive.

For our analysis, we will utilize the IMFs Fiscal Monitor categorization which breaks countries into three categories: advanced economics, emerging market, and low-income developing. This system is far from perfect, biased towards fiscal data and away from other barriers that determine a country's need and effectiveness of climate funding such as political stability. Countries in the low-income developing  group are designed to receive a larger share of funding than the formula outlined below spits out  (thereby reducing non-LDC developing countries share). This is an adjustable input a user can scenario plan with.

#### What determines a country's share of payment?
The goal of the payment side is to capture contribution, economic ability, and intent. To do this, payment share is determined based on three primary factors:
* **Share of the global warming problem**; metric: *cumulative emissions*: as the saying goes - you do the crime, you do the time. Countries who have historically emitted more, should (financially) suffer the consequences for their actions. They were the beneficiaries of industrial scaling and therefore should compensate for that benefit.
* **Financial muscle/ability to pay**; metric: *GDP per person x GDP*. By incorporating both GDP and GDP per person, the goal is to balance pure output with efficiency. Generally, the richer a country is, the easier it will be to compensate for their emissions. They will have an easier time borrowing and that financial outlay will represent a less per-person share. A bigger country should also contribute more.
  - GDP * per capita multiplier (at a range of 0.5 - 1.5)
  - GDP multiplier is the countries GDP per capita divided by the median country GDP per capita
* **Willingness to change**; metric: *renewable generation per person*. This is admittedly the most “out there” component of my equation. Beyond a countries willingness to be renewable there are other factors such as availability of natural occurring energy sources (e.g., geothermal). That aside, I still believed it to be valuable to reward and incentivize countries who have recognized the need to overhaul their energy sector to a higher share of renewables.

#### What determines a country's share of receiving?
Almost the opposite to payment, the reception of funds intends to encapsulate what countries need the funds the most. This is based on readiness, vulnerability, and their own economic ability to recover.
* **Vulnerability**; metric: *ND:vulnerability*. part of the [ND gain index](https://gain-new.crc.nd.edu/ranking) which summarizes a countries vulnerability to climate change based on 40 indicators from a Wolrd Bank data set. Categories include exposure, sensitivity and adaptive capacity.
* **Readiness / Capacity**; metric: *ND:readiness*. Assesses a "country's ability to leverage investments and convert them to adaptation actions" arond three core buckets: economic, social, and governance.
* **Environmental exposure:**; metric: **INFORM Risk score**. This is an IMF-driven indicator that incorporates three dimensions: hazard and exposure, volunerability and lack of coping capacity. The climate components include flood, stormes and drought. More info can be found [here](https://climatedata.imf.org/datasets/7cae02f84ed547fbbd6210d90da19879_0/about)
* **Financial Muscle**; metric: *GDP per person x GDP* - see above, a country's economic ability to mitigate and adapt to climate change using financial resources.

#### What should the total amount be?
Unsurprisingly, the range from scholars, developing countries, and developed countries range quite a bit. When considering the amount, there are several factors that should be considered to arrive at the final number. FIrst, the amount should at least **consider damages** likely driven by climate change now that we know wealthy nations bear the overwhelming responsibility. Then, we should talk about **progress** both in the forms of adaptation (e.g., new levee) and mitigation (cheap, clean energy). Unfortunately, all three categories are mere estimates which leaves plenty of room for debate. Researchers estimate the economic costs of loss and damage in developing nations to be $290B to $580B and rising (source). A report by the Independent High-Level Expert Group on Climate Finance argues that **at least 1 trillion USD** is needed per year to support developing countries. A far cry form from the $100B commitment made at recent COPs that have already been delinquent.

For the tool, the total amount will start at  $500B - an amount significantly higher than previous commitments but likely still (at least) half of what is needed. This amount is adjustable by the user.

## The Analysis
#### Components for the below analysis
Part of the fun of a dynamic tool is you can create infinite combinations and understand how the different weights impact funding. 

For this analysis, I've considered the following:
* **Donate** - GDP: 40%; Historical Emissions: 50%; Renewable Share of Energy Generation: 10%
* **Receive** - inverse of GDP: 50%; Vulnerability (defined as readiness, environmental exposure and general vulnerability): 50%

A few takeaways::
* the "contributing" countries is more top heavy with the top 10 countries representing more than 50% of all funds. The US and China alone account for 33%.
* there is a negative relationship between how vulnerable a country is and their readiness - more evidence and motivation to start funding **today**

#### Overview of net contributions

#### What else stands out?
## Conclusion
Going through this thought and data exercise exposed the complexity of the loss and damages fund. It is a problem ripe with sticky definitions, future unknowns, and a myriad of political & financial (dis)incentives all lending itself to debate rather than commitment. Likely, with many climate endeavors, the initial wave of commitments will be underwhelming. A “better than nothing” attitude will almost assuredly be needed in the short-term until a more robust program is established.

Let’s assume a fund and contribution amount is established with respective country contribution and allocation amounts set. What next - what should considerations be for operationalizing it? Sources Beyond the funding, how will future decisions be made? How will plans get approved and countries then held accountable for their commitments? Who will monitor the allocation funds and what should penalties look like?


**Funding Sources**
Diversify as much as possible beyond public finance through philanthropic funds and private funds
Use tools such as taxes to raise money for the fund in a clear, definable way
Determine if countries should be split into receivers/contributors or the fund should be thought of a shared investment with a more flexible structure

**Governance**
Who should get a seat on the fund and how should decisions be made?
Pushing policy through: consensus may be unrealistic for many decisions, and voting could slow down movement
Members: individual countries vs an  independent board be established
Key elements that should be front in center across each aspect: anti-corruption, transparency, inclusive, and accountability. Need to avoid the politicization

**Accessibility**
Minimize the accreditation requirements for developing countries to access the funds
Consider project based accreditation for faster approval, trigger-based systems for immediate concerns, minimum allocations
Ensure grants are set aside specifically for local, vulnerable communities

**Financing Instruments**
Grants are more valuable than loans since they do not compound debt and offer more flexibility for the recipient
Build capacity and catalyze future investment with more certainty through a more programmatic approach to finance. More can be done with a 5 year commitment then a series of checks implying uncertainty

**Distribution / Beneficiaries**
Flexible caps so all countries have access to funding
Assess and define what it means to be vulnerable
Prioritize marginalized groups

**Reporting & Accountability**
Balancing accountability with putting too much red tape around reporting for developing countries. Minimize the onus on developing countries by either providing support for reporting or training
Set strict rules with misappropriation evaluated by an organization like the World Bank with power to blacklist
Measure impact, share successes (and failures)

#### Inspired - take this to the next level?
Due to personal time constraints, I explored more of the system and general methodology and less of the “data science” side. If this analysis was of interest and you wanted to take it to the next level, a key piece will be how to update funding into the future. Developing models to predict what those key inputs (e.g., emissions) may look into the future can help countries earmark funding and be proactive. As stated earlier, this model is incredibly simple beyond the descriptive nature so being creative with other inputs to continue to drive equity is another way to bolster this analysis.

As for me, I will continue to monitor the evolution of this fund. Not only is it imperative to reduce emissions but it is simply the right thing to do.

