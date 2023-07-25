---
title: "The Energy Transition and Jobs"
date: 2023-07-25T02:01:58+05:30
description: "--"


tags: [analytics, economics, jobs]
---

![Oil Rig](https://colinpaulish.github.io/cp_hugo_nz30/img/oil_rig_small.png "worker at oil rig")
![Solar Maintenance](https://colinpaulish.github.io/cp_hugo_nz30/img/solar_fixing_small.png "worker afixing solar panel")


<div style="display: flex; justify-content: space-between;">
    <div style="flex: 1; padding: 10px;">
        <img src="https://colinpaulish.github.io/cp_hugo_nz30/img/oil_rig_small.png" alt="First Image" style="max-width: 100%; height: auto;">
    </div>
    <div style="flex: 1; padding: 10px;">
        <img src="https://colinpaulish.github.io/cp_hugo_nz30/img/solar_fixing_small.png" alt="Second Image" style="max-width: 100%; height: auto;">
    </div>
</div>

## Opening
It’s hard to fault policymakers and local leaders in fossil-fuel heavy regions for their pushback towards green legislation and general progress. Shifts in status quo are scary, particularly when the writing on the wall is in sharpie - renewable jobs are coming, and they will negatively impact fossil fuel employment. Industrial shifts can and have brought huge pain to governments, local economies, families, and people. From 1950 to 2000, the “Rust Belt’s” share of US manufacturing employment fell from one-half to one-third with similar magnitude drops when taking a step back calculating aggregate-level employment (source). If certain regions are upended with widespread turmoil during this shift to renewable energy, then we have failed. Instead of fighting policy change, policy leader conversations should shift to productive discussions that focus on the symbiotic potential of green jobs to the area. Two things can be true – we can see huge losses in fossil fuel jobs and see those same areas thrive.

In this post, my goal is to start the conversation and hopefully inspire more questions than what I answer. I open with a review of several academic studies that have forecasted employment change using different data analysis techniques. I will then shift to “real-life” data providing county-level analysis using data provided by the DoE. Here I  observe the distribution of fossil fuel and renewable energy jobs today and how that has changed over the last five years. I comment at the end what this all means and begin thoughts of how we can not just mitigate the negative potential in certain areas but set them up to thrive.


## Energy Transition - what we "know" today
My goal in this section is not to provide a comprehensive literature review of academic papers covering the potential impact of the labor economy during the shift. Rather, I hope to set up a structure of how we may want to to think of it by breaking the question into three core questions with other factors of consideration.

The first, and debatably most obvious and critical question is – will this shift lead to more or fewer jobs? Two recent papers paint an optimistic picture. Each uses employment factors which aim to estimate jobs based on investment and/or production of a commodity. In this analysis studying 28 EU countries + Norway, the authors fit an autoregressive regression time series model to estimate employment and concluded the transition will have a small but positive impact. This paper produced a more nuanced set of results but had similar findings. In their “aggressive” emission cutting scenario, jobs increased initially, peaking in 2025 with a net increase of close to one million jobs before seeing a decrease of ~2 million jobs as efficiency gains cut labor employment. This may seem like a suboptimal outcome, but it is important to note this study only looks at direct energy jobs and does not include labor related to transmission, battery storage, decentralized PV, eating, hydrogen and energy efficiency all of which are huge components of the renewable transition.

With greater confidence that the green transition will not lead to the destruction of energy jobs, we now move to a more nuanced question of how this job effect will be distributed spatially. Two pieces are needed to think through this – both the potential loss of fossil fuel jobs and the gain of green jobs. This paper provides useful views to understand employment in the fossil fuel industry with clear concentrations in the middle part of the country. This points to these communities having a larger-than-average impact of the transition. Conversely, green jobs have been concentrated in those same  [add in what we see from data analysis]. Anything from the USEER report?

So now we suspect energy jobs are here to stay and there is at least some relationship between loss and gain of green jobs with policy levers that can be deployed to even those delta. The final key question is how the mix of jobs may change. Returning again to this study, jobs by tech are more obvious. Coal, gas, and oil see huge decreases while green tech, primarily wind and solar, continue to see massive gains in employment. More interestingly, the mix of jobs shifts greatly. Jobs shift from fuel supply and production to operation & maintenance type jobs. Gains are also seen in manufacturing and construction & installation. This passes the logic test as energy systems are completely disrupted shifting from massive regional energy suppliers to tens, hundreds of thousands of distributed energy systems (e.g., rooftop solar).

A few other topics of interest for me include wages, skills, labor mobility, and tech (productivity) advancements. I hope to explore one (or several) of these at a future point.

## Painting the Picture Energy Jobs Today
This section is really all about understanding the who behind all of these policy debates. When a policy report describes a uniform cut in traditional energy jobs, who is impacted? Conversely, an investment that is expected to generate largely clean jobs may target specific areas, but it may also be relevant to see who holds those jobs and have a more established talent pool today.
 
`Who?`
The DOE releases an annual Energy and Employment Report (USEER) which tracks employment trends across the energy sector using both labor and survey data. By combining these approaches, the report can compartmentalize jobs by sectors (e.g., wind vs vehicles) while supplementing it with the underlying demographics of those workers. This analysis covers X million workers. A few highlights:
* Women range from 23-32% of the workforce, sector dependent
* Veterans consistently are overrepresented
* Black and hispanic populations are underrepresented
* Generally, the workforce is younger

`Where`
![Fossil Fuel Jobs](https://colinpaulish.github.io/cp_hugo_nz30/img/current_fossil_fuels.png "fossil fuel quintile map")
*Quintile county map of fossil fuel jobs as a percent of total employment*

The above visual depicts quintiles of fossil fuel jobs as a percentage of the population, the darker the shade the higher the share. The disparities are evident visually with concentrations of fossil fuel jobs in Texas, the midwest and portions of the Appalachia. Possibly no delineation is more noticeable than West Virginia and its neighbor, Virginia. 87% of West Virginia’s counties are in the highest quintile versus just 18% for its neighbor.

![Fossil Fuel x Clean](https://colinpaulish.github.io/cp_hugo_nz30/img/x_dirty_y_clean_politics_pop.png "state scatter")
*X axis = dirty as a %; Y = clean; color = politics, size = population*


This graph can start to identify states at large that may be more sensitive to shifts particularly when there is an imbalance between exposure and reliance on clean vs fossil fuel energy jobs. The bottom right quadrant with states such as West Virginia being a prime example of the third highest share of fossil fuel jobs as a share of their population but the bottom five for clean. Analyses like these can start to proactively identify hesitant policymakers and communities with the aim to design solutions that work for both the climate and their constituents.

![WY and VT](https://colinpaulish.github.io/cp_hugo_nz30/img/wy_vt_x_dirty_y_clean.png "WY and VT scatter")
*X axis = dirty as a %; Y = clean; color = state -- WY is blue, VT red, size = population*

Wyoming (blue) and Vermont (red) counties are extreme but real examples that capture the difference in community reliance on energy jobs. Immediately, it becomes clear no Vermont county has more than 2% of its population working in fossil fuels while Wyoming has a county with 15% in the industry. Conversely, most Wyoming counties have ~1% working in clean energy jobs.


`Relationships`
To start, there is not a strong relationship at the county level between clean and fossil fuel energy jobs with just an 11% r-squared value. Another interesting observation is the relationship that does exist between income and energy jobs. Median household income is very strongly negatively correlated with fossil fuel employment and lesser so with green energy jobs. The final relationship to highlight is political – the share to which a county voted Republican in the 2020 election has almost no predictive power in fossil fuel employment as a share of population.

## Looking to the Future
Let’s start general. For this section, I am utilizing USEER’s annual report which can be found here. The overall takeaway is many of the 3.9% job growth from 2021 to 2022 can be claimed by clean jobs. Clean vehicles accounted for 59% of all motor vehicle jobs with wind, grid modernization, and battery jobs increasing at some of the highest rates. Moreover, energy efficiency type jobs accounted for 17% of all growth. Per their report, North Dakota, West Virginia, New Mexico and Wyoming experienced the largest growth in fuels jobs - the usual suspects. Conversely, clean jobs represented a more diverse geographic and political footprint. Total clean jobs was dominated by California, Texas and New York. Energy efficiency growth leaders include Nevada, New Mexico, Oklaohom and New Jersey.

Let’s move to more detailed analysis from my data set and code. It is too early to understand the shifts in energy employment that are expected to unfold over the next several decades. Early signals may just be noise as we await large shifts to come from investments such as the IRA and political shifts next year. That said, below are five year changes in fossil fuel (left) and clean (right) energy jobs from 2015 to 2020. Fossil fuel jobs are being added in a more concentrated nature compared to clean jobs. Just from quick observation, fossil fuel jobs are being added along the east coast with particular concentrations in the South and in the Great Plains in states such as South Dakota. Clean jobs certainly have concentrations as well, with similar increases in the Great Plains and scattered but heavier uptake in the midwest and Texas.

![Fossil Fuel x Clean](https://colinpaulish.github.io/cp_hugo_nz30/img/dirty_clean_change.png "state scatter")
*Fossil fuel job change (left) by county vs clean energy job change (right)*


## Conclusion
This article hopefully ignited brain waves to start thinking about how this large industrial transition to clean energy impacts the economy and local communities. The goal is clear - to minimize emissions by transitioning individuals and jobs from fossil fuels to green in an equitable manner.

The implications are massive. Beyond the thousands of individuals impacted, the success of this effort will have huge implications on future policies and elections. It is important we don’t leave anyone behind, so it is in our best collective interests to understand what the future may look like and start to take action on policies to mitigate future losses. This includes upskilling, investing strategically, and, most importantly, talking about it.

It is a fact that a greener energy future brings less environmental risk and cleaner air. Early studies indicate that this future also comes with a similar level of energy jobs with shifts in scope and technology of focus. What is harder to predict is who is left behind, where are they, and what we can do about it. This will be critical. We need everyone on board and do not want anyone to be left behind.
