---
title: "Charging Optimization"
date: 2024-06-12T02:01:58+05:30
description: "--"


tags: [Python, Optimization, Geospatial Analytics]
---

## San Diego Charging Optimization [in progress]



### Setting the scene 

The concept is simple. When low on fuel, instead of pulling up to a station and powering your car with gas, electricity flows instead. The long-term strategy is also simple - in a green future, these electric vehicle (EV) charging ports will be everywhere supplying a high-voltage supply of electricity from a local green energy source. Transportation decarbonized with a fleet of easier to assemble, cheaper to buy, and quieter to drive vehicles zooming across our motorways.

Unfortunately, there is not just a catch but multiple. Let’s think of these in the flow of a customer in need of a charge.

**Finding a charger:** *noticing your range at under 50, you decide it's time to top up. The problem: there isn’t a convenient charging station - one that is either nearby or enroute to your destination.*

Per Blink, by 2030, there needs to be 20x the charging stations to meet the demand under the desired scenario where >50% of all vehicles sold are zero-emission (source). There is some runway to meet that goal, but the pure scale is frightening. To be clear, we are at a deficit today for an optimal EV:charger ratio. Additionally, studies show that these stations are typically concentrated in population centers so if you find yourself low on charge in a more rural area you may be out of luck. Overall, the average number of gas pumps per 1,000 miles is 104. That’s a gas pump nearly every 10 miles. And EV charging stations? 22 per 1,000 miles. (source). 

**Reliability of the station:** *you’ve made it to the charger. Time to take a breath of relief. After some fumbling over downloading an app and authorizing payment you finally connect to your car. An error appears on the screen.* 
According to the Electrification Institute, one out of every five visits ends without charging. The main culprits are station connectivity (55%) and software issues (38%) (source). The Biden administration aims to require a reliability level of 97% (meaning the charger is working at least that proportion of the time). The figure today is closer to 72.5% (source). Lack of data, people, and growing pains of new tech and customer service are all culprits. 

**Speed to charge:** *alas, you have found a station that works and your vehicle is indicating charging has begun. Before catching up on emails, you take a quick glance at your dashboard monitor - it is estimating an hour to charge!*

Per the US Department of Transportation, there are currently three levels of charging.

* Level 1: a standard outlet providing 120V AC will charge about 2-5 miles per hour
* Level 2: this can be installed for a normal outlet and provides 240V AC charging 10-20 miles per hour
* DC fast chargers (most of the new public infrastructure investment): provides a larger range from 400-1000V AC of power charging 180-240 miles per hour

 A couple of things should be clear. First is that there is a massive difference based on the voltage supplied by that station. Second, and more frighteningly, is the massive delta between the fastest DC charger and its gas pump complement. As the US builds out its infrastructure network, it is imperative that the proportion of stations that are DC fast charging stations should approach 100% and investments in speed improvements should be prioritized. 

### Analysis

This analysis aims to investigate a critical piece of the EV ownership experience and current barrier to entry, EV charging infrastructure. Using Python, I cobbled together San Diego County charging locations and traffic flow data to answer two key questions using an optimization algorithm:
Are chargers currently placed optimally?
As infrastructure within county lines grows, where should subsequent chargers be built?

The culmination of the data manipulation and optimization culminates in a user-friendly Tableau tool that visualizes current charging locations and user-set future charging locations. The optimization engine aims to minimize the ratio of traffic to “charger score.” That is, if there is more traffic around a particular area, the goal is to have more nearby chargers. The charger score is the sum the inverse distance in miles of all locations. As a simple example, let’s assume there are only 3 chargers in San Diego county that are 1 mile, 4 miles, and 10 miles away. The charger score would therefore be 1.35 (1/1 + ¼ +1/10).  

Like many other analyses, I simplified the approach, Notably, I did not restrict where within a lat/long coordinates chargers could be placed so it is likely the optimization may spit out a location not technologically of politically feasible. 

I have intentionally left out many of the technological pieces of charging - it is best to leave the mechanics and innovations to the scientits, engineers and mechanics powering our EV world. 
methods

### Why this all matters
The motivation for this analysis is two-fold: 1) EVs are a critical piece to decarbonization and a huge deterrence is confidence in the charging infrastructure; 2) EV adoption is growing (albeit at a slower rate partly due to charging concerns) magnifying this issue. Add those to the context that EV owners are happy - according to Plug in America’s Driver survey, 90% of EV drivers report  that they are likely or very likely to purchase an EV as their next vehicle (source). To decarbonize we need to not just convince drivers to switch from combustion to battery but ensure that experience is good. 

**Today**
Despite doomsday click-bait headlines, EVs are growing quickly. According to Marketwatch, 1.6M EVs were sold in 2023, an increase of 60% from 2022 and 5x from 2020 (source). Although the growth rate is expected to start to slow with uptake resembling a more traditional S-curve adoption rate, the number of EVs on the road will only continue to grow over time. The number of chargers, as mentioned above, are growing as well but at a pace inadequate to meet growing demand. To combat this, President Biden allocated $7.5B in EV charging funding as part of the Bipartisan Infrastructure Law with the sole purpose of, “...(to) support installations of charging infrastructure, as well as dozens of other federal initiatives designed to drive domestic manufacturing and build a national network of EV charging” (source).

A few pieces I want to call out as things to think about that are current as of me writing this (May, 2024):
* Why the Federal money for private infrastructure? A couple of reasons. First, the aim is to compress the time horizon as quickly as possible. Second, is to disrupt the economics  of an infrastructure investment such as charging stations. A station is profitable if it is being used (utilization rate) so the owners of each station want a higher utilization to generate a greater RoI. This could lead itself to an undersupply of chargers to maximize profits. By attaching funding to higher volumes, the Federal government is overcoming this market failure
* Second, and hot off the press, is Elon’s firing of Tesla’s charging team. This is big news as Tesla has the most robust (and reliable) charging network AND recent partnerships have made it so other companies are more integrated in their charging network than ever before. Having the right number of chargers matters. As mentioned, we need chargers to convince folks to buy an EV. Here are just a few numbers that tell the story:

* Scale needed: forty-two percent of respondents in this group, who we refer to as skeptical EV buyers, state that they will only move forward with an EV purchase if public-charger availability is equivalent to that of current gas stations (source)
* Confidence: Americans express limited confidence that the country will build the necessary infrastructure to support large numbers of EVs on the roads. Some 17% say they are extremely or very confident this will happen, while 30% are somewhat confident. And 53% are not too or not at all confident (source)
* Also registering as a primary roadblock for not buying an EV among 60% of Americans is charging station scarcity. In other words, some shoppers worry about being able to find a charger when away from home

### Tool findings

### Thinking Ahead
This analysis really covers just one element - volume when considering where to place EVs. Other pieces that are limitations of this analysis include feasibility of a location (e.g., electricity flow, zoning), ensuring equitable distribution, and understanding current EV charging station usage. Relatedly, two data elements I wish I had are EV purchases (and travel) data to increase confidence in where EV drivers are traveling and charging station usage data to understand utilization (a low utilization may indicate no more chargers are needed in that location), reliability, and intra-day temporal usage. 

All that said, a data driven approach should be used as a starting point for designing EV charging location strategies. Different approaches should be tested across the country converging on an approach that works best (balanced utilization, low waiting times, equitable access). More importantly, more stations are needed to meet the growing demand, instill confidence in potential adopters, and improve the overall experience. 

Be on the lookout for how the EV charging count is growing in your area over the next 5-10 years, I imagine it will be significant. In the meantime, dream of a world of quieter cars, cheaper electricity, and a greener world. 


