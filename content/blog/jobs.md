---
title: "Impact of Energy Transition on Jobs"
date: 2023-011-25T02:01:58+05:30
description: "--"


tags: [Python, Tableau, APIs, Workforce Planning]
---

![Future Energy](https://colinpaulish.github.io/cp_hugo_nz30/img/energy_together.png "worker at oil rig")


<div style="display: flex; justify-content: space-between;">
    <div style="flex: 1; padding: 10px;">
        <img src="https://colinpaulish.github.io/cp_hugo_nz30/img/oil_rig_small.png" alt="First Image" style="max-width: 100%; height: auto;">
    </div>
    <div style="flex: 1; padding: 10px;">
        <img src="https://colinpaulish.github.io/cp_hugo_nz30/img/solar_fixing_small.png" alt="Second Image" style="max-width: 100%; height: auto;">
    </div>
</div>

## Opening
It’s hard to fault policymakers and local leaders in fossil-fuel heavy regions for their pushback towards green legislation. Shifts in status quo are scary, particularly when the writing on the wall is in sharpie - **renewable jobs are coming, and they will negatively impact fossil fuel employment**. Industrial shifts can and have brought huge pain to governments, local economies, families, and people. From 1950 to 2000, the “Rust Belt’s” share of US manufacturing employment fell from one-half to one-third with similar magnitude drops when taking a step back calculating aggregate-level employment. More relatedly to energy, research suggests that when energy workers are let go either because their employer shut down or downsized (often in the times of low energy prices) they “earn 13 to 25 percent below their pre-displacement salaries [(Labor Market White Paper)](https://economics.ucr.edu/wp-content/uploads/2019/10/Ohanian-paper-for-4-13-18-seminar-1.pdf)". Quite plainly, if certain regions are upended with widespread turmoil during this shift to renewable energy, then we have failed. Instead of fighting policy change, policy leader conversations should shift to productive discussions that focus on the symbiotic potential of green jobs to the area. **Two things can be true – we can see huge losses in fossil fuel jobs and see those same areas thrive**.

In this post, my goal is to start the conversation and hopefully inspire more questions than what I answer. I open with a review of several academic studies that have forecasted employment change using different data analysis techniques. I will then shift to “real-life” data providing county-level analysis using data provided by the Department of Energy. I comment at the end what this all means and pose different policy levers at our disposal to mitigate the effects.


## Energy Transition - what we "know" today
To be clear, this is not a comprehensive literature review of academic papers covering the potential impact of the labor economy as a result of an industrial shift. Rather, I hope to set up a structure of how we may want to to think of it by breaking the question into three core questions.

The first, and debatably most obvious and critical question is – **will this shift lead to more or fewer jobs?** Two recent papers paint an optimistic picture. Each uses employment factors which aim to estimate jobs based on investment and/or production of a commodity. In [this analysis](https://www.tandfonline.com/doi/epdf/10.1080/13504509.2022.2078902?needAccess=true&role=button) studying 28 EU countries + Norway, the authors fit an autoregressive regression time series model to estimate employment and concluded the transition will have a **small but positive impact**. This [paper](https://www.nber.org/system/files/working_papers/w30871/w30871.pdf) produced a more nuanced set of results but had similar findings. In their “aggressive” emission cutting scenario, jobs increased initially, peaking in 2025 with a net increase of close to one million jobs before seeing a decrease of ~2 million jobs as efficiency gains cut labor employment. This may seem like a suboptimal outcome, but it is important to note this study only looks at direct energy jobs and does not include labor related to transmission, battery storage, decentralized PV, eating, hydrogen and energy efficiency all of which are huge components of the renewable transition.

With greater confidence that the green transition will not lead to the destruction of energy jobs in aggregate, we now move to a more nuanced question of **how this job effect will be distributed spatially?** Two pieces are needed to think through this – both the potential loss of fossil fuel jobs and the gain of green jobs. This [paper](https://www.nber.org/system/files/working_papers/w30871/w30871.pdf) provides useful views to understand employment in the fossil fuel industry, an industry that pays relatively high wages to less educated workers. In this paper, the author focuses on direct use of fossil fuels. To understand the vulnerability of job loss, the author looks at employment share across three “direct” fossil fuel employment  industries including fuel extraction & refining, intensive manufacturing, and electric power generation. Unsurprisingly, each had unique pockets of elevated employment share. The overall takeaway is that **these jobs are not distributed evenly** and that many of the jobs are concentrated in the Great Plains and pockets of the eastern corridor (primarily manufacturing in the South). This is a trend we will see below in my own analysis.

So now we suspect energy jobs are here to stay, but that change in employment will likely not be evenly distributed. The final key question is **how the mix of jobs may change**. Returning again to [this study](https://www.sciencedirect.com/science/article/pii/S0301421521005073), jobs by tech are more obvious. Coal, gas, and oil see huge decreases while green tech, primarily wind and solar, continue to see massive gains in employment. More interestingly, the mix of jobs shifts greatly. **Jobs shift from fuel supply and production to operation & maintenance type jobs. Gains are also seen in manufacturing and construction & installation.** This passes the logic test as energy systems are completely disrupted shifting from massive regional energy suppliers to tens, hundreds of thousands of distributed energy systems (e.g., rooftop solar).

A few other topics of interest for me include wages, skills, labor mobility, and tech (productivity) advancements. I hope to explore one (or several) of these at a future point.

At a very high  level, energy will remain a dominant industry in the USA but it will increasingly look different as the transition matures. Jobs will likely be more evenly distributed and shifted to operations & maintenance type jobs away from large-scale extraction and refining.


## Painting the Picture Energy Jobs Today
This section is really all about understanding the who behind all of these policy debates. When a policy report describes a cut in traditional energy jobs, who is impacted? Conversely, an investment that is expected to generate largely clean jobs may target specific areas, but it may also be relevant to know where those jobs are today.
 
`Who?`

The DOE releases an annual Energy and Employment Report (USEER) which tracks employment trends across the energy sector using both labor and survey data. By combining these approaches, the report can compartmentalize jobs by sectors (e.g., wind vs vehicles) while supplementing it with the underlying demographics of those workers.  A few highlights:
* Women range from 23-32% of the workforce, sector dependent
* Veterans consistently are overrepresented relative to their share of the overall population
* Black and hispanic populations are underrepresented
* Generally, the workforce is younger

`Where`

![Fossil Fuel Jobs](https://colinpaulish.github.io/cp_hugo_nz30/img/current_fossil_fuels.png "fossil fuel quintile map")
*Quintile county map of fossil fuel jobs as a percent of total employment*

The above visual organizes fossil fuel employment share into quintiles. The darker the shade, the higher the share. The disparities are evident visually with concentrations of fossil fuel jobs in Texas, the midwest and portions of the Appalachia. Possibly no delineation is more noticeable than West Virginia and its neighbor, Virginia. 87% of West Virginia’s counties are in the highest quintile versus just 18% for its neighbor. A larger geographic concentration can be seen across the Great Plains from West Texas up to Montana.

![Fossil Fuel x Clean](https://colinpaulish.github.io/cp_hugo_nz30/img/x_dirty_y_clean_politics_pop.png "state scatter")
*X axis = dirty as a %; Y = clean; color = politics, size = population*


This scatterplot adds in a few more layers this time at the state level. Plotting share of fossil fuel vs clean energy jobs helps us start to identify states  that may be more sensitive to shifts away from fossil fuel jobs while also identifying states that may be the beneficiaries under the status quo. The bottom right quadrant identifies states particularly at risk given their larger than average share of fossil fuel employment and below average clear energy jobs. Again, pointing to West Virginia as a prime example with the third highest share of fossil fuel jobs while in the bottom five for clean jobs. This graph also starts to descriptively layer on top high-level relationships. Not unsurprisingly, fossil fuel heavy states are dominated by a population that tends to vote more Republican while more clean energy jobs are found in democratically-controlled regions.  Analyses like these can start to proactively identify hesitant policymakers and communities with the aim to design solutions that work for both the climate and their constituents.

![WY and VT](https://colinpaulish.github.io/cp_hugo_nz30/img/wy_vt_x_dirty_y_clean.png "WY and VT scatter")
*X axis = dirty as a %; Y = clean; color = state -- WY is blue, VT red, size = population*

If we “double-click” into a few states, we can start to understand nuances at a more local level. Wyoming (blue) and Vermont (red) counties are extreme but real examples that capture the difference in community reliance on energy jobs. Vermont does not have county with more than 2% of its population working in fossil fuels while Wyoming has a county 7x that share. Conversely, most Wyoming counties have ~1% working in clean energy jobs showing a huge disparity. Beyond the state comparison and general trends, it is important to note that difference across communities. It is true that Wyoming is a higher-than-average employer of fossil fuel jobs, but that share ranges quite a bit. Identifying and then understanding that is important to shy away from blanket capital expenditures to more targeted investment for the communities that need it the most.


`Relationships`
To start, there is not a strong relationship at the county level between clean and fossil fuel energy jobs with just an 11% r-squared value. A relationship that does exist is between income and energy jobs. Median household income is very strongly negatively correlated with fossil fuel employment and also negatively correlated with green energy jobs but at a much lower factor. The final relationship to highlight is political – the share to which a county voted Republican in the 2020 election has just a small predictive relationship fossil fuel employment as a share of population, a surprising result that could be due to the higher level of analysis conducted here.

## Looking to the Future
To start, let’s investigate big picture trends outlined in [USEER’s annual report](https://www.energy.gov/policy/us-energy-employment-jobs-report-useer). The overall takeaway is that much of the 3.9% job growth from 2021 to 2022 can be claimed by clean jobs. Clean vehicles accounted for 59% of all new motor vehicle jobs with wind, grid modernization, and battery jobs all experiencing some of the highest growth rates. Moreover, energy efficiency type jobs accounted for 17% of all growth. From a spatial lens, North Dakota, West Virginia, New Mexico and Wyoming experienced the largest growth in fuels jobs. Conversely, clean jobs represented a more diverse geographic and political footprint. Total clean jobs were dominated by California, Texas and New York. Energy efficiency growth rate leaders include Nevada, New Mexico, Oklaohom and New Jersey.

I hoped to uncover potential signals of what may be a sign to come at a soon-to-be larger scale. Admittedly, it is too early to say with any confidence what those shifts will look like as they unfold over the next several decades and early signals may just be noise. That said, it is important to monitor these shifts and they could provide early indications of what is to come. Below are five year changes in fossil fuel (left) and clean (right) energy jobs from 2015 to 2020. Fossil fuel jobs are being added in a more concentrated nature compared to clean jobs. There is a noticeable uptick in fossil fuel jobs along the east coast with particular concentrations in the South and in the Great Plains in states such as South Dakota. Clean jobs certainly have concentrations as well, with similar increases in the Great Plains, Midwest, and Texas but are certainly more distributed.


![Fossil Fuel x Clean](https://colinpaulish.github.io/cp_hugo_nz30/img/dirty_clean_change.png "state scatter")
*Fossil fuel job change (left) by county vs clean energy job change (right)*


## Conclusion
This article hopefully helped you start to think critically about how this large industrial transition to clean energy impacts the economy and local communities. The **goal is clear - to minimize emissions by transitioning individuals and jobs from fossil fuels to green in an equitable manner.**

The implications are massive. Beyond the thousands of individuals impacted, the success of this effort will have huge implications on future policies and elections. It is important **we don’t leave anyone behind**, so it is in our best collective interests to understand what the future may look like and start to take action on policies to mitigate future losses. Thankfully, this is not the first energy transition the US has gone through - after coal employment peaked at 234,000 workers in 1979 it declined precipitously, almost halving the next two decades before reaching 13,000 today. An additional complication was the clustering of employment in the Appalachia areas. Unfortunately, the results are bleak. As areas saw larger impacts of coal employment, their employment and wages rates declined and persisted for 20 years despite significant handouts. As a result, people migrated leaving a less educated and more government-funded group behind [source](https://www.nber.org/system/files/working_papers/w30871/w30871.pdf).

Policymakers should understand the lessons from this and be ready this time. Policy should be thought of in both the short and long-term. In the short-term, it is still necessary to supply former workers with an income stream as they look through work via a social safety net like unemployment insurance. Thankfully, that is not the only arrow in our quiver. Local impact analysis should assess the potential transition effect and underlying population and design programs fitted to the community. This may include outside capital investment in new businesses, large workforce development programs, and upskilling in industries that remain to boost productivity.

**It is a fact that a greener energy future brings less environmental risk and cleaner air**. Early studies indicate that this future also comes with a similar level of energy jobs with shifts in scope and technology of focus. What is harder to predict and plan for is who is left behind, where are they, and what we can do about it. **It is important to get out ahead and start talking about it - we owe it to ourselves.**

