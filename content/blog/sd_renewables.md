---
title: "Local Context: San Diego and Solar"
date: 2023-06-20T02:01:58+05:30
description: "It doesn't take much poking around to find the lofty goal set by San Diego's Energy Department to '...add additional renewable electricity supply to achieve 100 percent renewable electricity citywide.' Unfortunately, talk is cheap and the energy transformation is not. In this analysis, I deep dive on publicly available data to understand progress and, most importantly, discuss can we learn from this case study.
"


tags: [data, visualization, local]
---

![Futuristic City](https://colinpaulish.github.io/cp_hugo_nz30/img/renewable_city_small.png "futuristic city")


## Opening
Cities will be crucial in leading innovation, policy change, and enacting ambitious legislation set force by policies such as the Inflation Reduction Act. In this article, I examine how San Diego has performed in adding renewable energy to the grid via solar highlighting pertinent trends and differences. Please play with [this Tableau dashboard](https://public.tableau.com/app/profile/colin.paulish) I put together to power this analysis drawing upon San Diego solar data and ACS community information.

![Tableau Dash](https://colinpaulish.github.io/cp_hugo_nz30/img/sd_tableau_dash.jpg "Tableau analysis")


## Context
On June 1st, 2017, Trump formally withdrew the United States from the Paris Climate Agreement. Hours later, three governors from California, Washington, and New York countered forming the U.S. Climate Alliance, a coalition centered around reducing collective net GHG through policy. Today, 25 governors have joined.

Now, more than halfway through Biden’s first term presidency, the Federal government's position on climate change is drastically different. So far, Biden has passed a trio of bills referred to as Uncles Bill, Chip and Ira (Infrastructure Investment & Jobs, CHIPS, Inflation Reduction Act respectively), the latter alone the biggest investment in mitigating climate change in this nation’s history. With huge funding already appropriated towards climate change and a split Congress, it is unlikely any new, large Federal funding will pass in the near-term.  Whereas it was on the states to lead the way on policy under Trump’s cloudy climate skies, it is now on them to lead the charge on implementing many of the incentives to reach its goal of reducing critical emissions between 31 and 44 percent of 2005 levels. As the seasoned climate reporter David Roberts astutely asks, are they ready?

That brings us to our cities which serve in unique and powerful positions. The International Energy Agency estimates that urban areas are responsible for 71% of energy related carbon emissions. More and more people are moving to urban areas, a trend that is expected to continue. Thankfully, many cities are using this power for good by leading innovation on climate change. As of 2021, 58 of the 100 largest US cities had an approved climate action plan (1). Here in the States, cities are on track to reduce emissions by 32% below 2005 levels by 2025, ahead of goals set out by the Paris Climate Agreement. Take a look at how the biggest city, NYC, is tracking and providing transparency towards thief goals with their climate dashboard here.

In terms of what’s on their minds, In a recent meta-analysis conducted by the National League of Cities (NLC) on fifty recent city plans, five themes stood out (2):
1. Boosting energy efficient buildings
2. Investing in EV infrastructure
3. Optimizing Waste Operations
4. Improving Access to public Transportation
5. Investing in Renewable Energy


In this project, I am focusing on the fifth theme, driving renewable energy. Beyond an interest, as our energy system moves towards electrifying (almost) everything, more and more clean energy will be demanded. A huge source of that, per Princeton’s futuristic Net-Zero America report is solar’s 2-5x increase to today’s totals (source). To understand progress, I deep dove on  the city I live in, San Diego. In particular, I looked at geographic and temporal trends to uncover what we know, what capacity may look like in the future and what this means for other cities across the US.

## Data Sources
To conduct this analysis, I utilized three data sets:

1. Renewable energy data from California Distributed Generation Statistics which can be found here includes solar projects from 1982 to present. This data is at the project level.
2. Zip code data from Census compiled into a nifty package, zipcodeR where I pulled important metrics such as household income and used a census tract to zip code mapping table created as part of this package.
3. Census ACS API where I utilized data from its 2021 survey where I pulled data at the Census Tract level and then rolled up to the zip code level to get many zip code specific proportions such as percent renter

Both zip code data sets were joined to the project level data.

## Themes and Takeaways
Through the Tableau dashboard built and some basic statistical analysis, there are three themes that emerged with important policy considerations. All of these analyses are extremely surface-level and would require more digging (and time) – however, I still believe they are worth calling out as topics to further explore.


#### There are significant differences in projects by community. Lower income areas are installing solar at a significantly different rate (renting as factor here). Despite falling behind, solar has picked up in lower income areas.

`What the data says`: Descriptively, the trend is clear. The four most affluent zip codes have the highest solar installation rate with the inverse true for less affluent areas. Statistically, if you plot household income by projects per household, a linear explainer captures 68% of the variation with a significant p-value. There are likely many factors contributing to this divide. For example, lower income communities are more likely to rent than own with utility bills paid by the renter. This creates a misaligned incentive structure where the benefits of the upfront cost do not flow back to the investor. Another interesting observation is that cost per watt of energy is higher in low income areas which are the communities who can least afford it.

`Why this matters`: Low income consumers pay a much higher proportion of their income on energy. A recent report from the American Council for an Energy-Efficient Economy (AMCEE) found that one-fourth of all U.S. households have a high energy burden meaning they spend >6% of their income on utility bills. That number jumps to two-thirds when looking at just low-income households. Those burdens are not spread evenly through society as black and hispanic households have an energy burden that is 43% and 20% higher than white households respectively (source).

`What we can do about it`: Generally, programs and policies need to be flexible, tailored, and cost effective for local residents. To be empowered, both sides of the equation - risk and benefit can be tinkered with from a variety of policies. Below are three core solution groupings the US Department of Energy outlines with just a couple of examples from an array provided (source).
1. Compensation mechanisms - the implementation of net metering allowing customers to financially benefit when they are producing excess energy from their solar panels and/or community solar where benefits of usually an offsite solar project flows to multiple customers
2. Direct Incentives - providing tax credits and rebates with additional benefits for low income households
3. Financing and incentives - generally attempting to lower the risk for lender and cost of financing such as on-bill repayment where the repayment cost is offset by the benefit of the solar generation or programs that provide a safety net for banks such as loan guarantees to lower the financing risk for both the purchaser and bank.

#### After growth, stalls in key metrics: cost per watt, capacity per project, number of projects, application processing

`What the data says`: In an ideal world, modular solar residential would continue to improve creating a positive feedback loop. Lower prices would drive demand, whose projects would be approved faster (reducing risk of a change of heart), and those projects would produce more solar capacity. Unfortunately, this does not appear to be the case. Over the long-run, most of these metrics have come down but have stagnated over the last 5-10 years. Capacity and cost has fluctuated with highest efficiencies in 2021 while the application process has halved over the last decade, there has been little change over the last five years. .

`Why this matters`: Generating clean energy from your home has never been easier (or more prominent). That said, we need all of the energy we can get and a lot more of it. A byproduct of improving efficiency and lowering costs is the reduction of both logistic and cost-related barriers which, in turn, should drive more to make the jump to solar.

`What we can do about it`: Thankfully, policy can be (and is) very helpful here. Incentives primarily through the IRA passes on tax credits that reduce the final bill for consumers. A recent Swedish study found subsidies and peer effects are significant factors increasing likelihood to adopt (source).

#### Commercial projects lag behind residential and have fallen quickly (237 in 2016, 40 in 2022)

`What the data says`: Investment in solar in the commercial lags significantly behind residential and has followed a very different trajectory. Peaking in 2016, prjects have fallen 83% to just 40 in the most recent year. This trend persists despite a lower average cost per watt of energy. This caught my eye as, in theory, businesses would have the greatest incentive to invest in cheap energy given a higher footprint per square foot, profit maximizing incentives, and often longer timelines.

`Why this matters`: In 2021, San Diego had 90,000 businesses. Despite many unlikely to have a storefront, businesses represent a large physical and carbon footprint. Reducing emissions in this sector, often concentrated in dense, urban areas will also improve air quality.

`What we can do about it`: Not surprisingly, the most effective policies are financially driven via incentives primarily deployed in the form of tax benefits. This includes a federal investment tax credit (ITC) which provides a credit at 26% of the value of the of the project available to both consumers and businesses. Modified Accelerated Cost Recovery System (MACRS) however is available to only businesses which allows businesses to lower their taxable earnings based on the depreciation level of your solar asset. Beyond tax incentives, solar performance based incentives is another creative category where a state or utility will offer an incentive rate for each kilowatt-hour of solar produced (source).

![test4](img/renewable_city_super_small.png)
