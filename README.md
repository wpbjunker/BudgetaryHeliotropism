
# An Exploration of Budgetary Heliotropism at NASA: Does Funding Follow the Solar Cycle?


## 1. Research Question

Does NASA's budget, as well as funding for the Heliophysics Division, vary alongside the solar cycle? 

The effects of solar activity on society are increasingly relevant as economic, social, and cultural activity is increasingly dependent on electric power. The North American electric grid is the infrastructure on which this activity is built, and under typical conditions it is stable, extensive, and fault-tolerant. However, this doesn't mean the system is fool-proof. Extreme weather events present serious risk to the health of electric grids. When too much power is running through the system - like when everyone runs their A/Cs at full blast during a severe heatwave - the system becomes overloaded, starting fires, blowing out substations, and taking out power lines. Rarely, such events pervade beyond a local level into a regional issue. 

This happened to the Electric Reliability Council of Texas (ERCOT, Texas power grid) in the blizzard of February 2021. When households and businesses used ovens, furnaces, and plug-in heaters to combat record freezing temperatures, ERCOT's capacity was grossly exceeded. Catastrophic failure was averted by mere minutes. The blizzard caused $195 billion in property damages, and resulted in the deaths of at least 246 people. Yet the destruction would have been far greater had there been a complete system collapse. Replacing ruined equipment presents a dire logistics problem when an extreme volume is required all at once; existing supply chains are slow to adapt to sudden spikes in demand. Had the worst-case scenario occurred with ERCOT, the supply lag would have left Texas with significantly reduced power for months and incurred an order of magnitude more costs in deaths, damages, and economic losses.

Weather events like extreme heat or cold, increasingly frequent due to climate change, are putting mounting stress on electric grids. Yet there is an unlikely source of risk that presents a potentially greater threat: solar weather. When it comes to outages, the more widespread, the bigger the problem is. The 2021 Texas blizzard was a region-level event. Coronal mass ejections (CMEs) of plasma, commonly associated with solar flares, have the potential to be global disasters. You've likely seen the effects of CMEs before: the aurora borealis, or "northern lights", results from the interaction between Earth's magnetosphere and plasma shot from the Sun. In 2025, we're currently at a solar maximum, and you might have noticed that we're seeing auroras more frequently and further from the poles. But aside from these atmospheric displays, CMEs also have the power to wreak havoc on radio communications and induce currents in electric lines, potentially causing voltage collapse, or worse, destroying grid equipment. The 1989 Quebec Geomagnetic Storm, the strongest of the past century, took out the Hydro-Quebec grid, and nearly caused cascading failures in the US Northeast and Mid-Atlantic areas. The aurora was observed as far south as Florida, and the damage was valued at $13.2 Billion. 

But we know for certain this is a mere drop in the bucket, compared to the cataclysm of a Carrington-level storm. Our understanding of the 1859 Carrington Event is limited, the study of heliophysics was still in its nascency at the time. Journalistic accounts indicate an auroral display so impressive in its effects, people rose for work mistaking it for the dawn, and read clearly from its light in the middle of the night. The aurora could be seen in Panama, 18 degrees from the equator. In the United States, the telegraph network was overloaded with induced current, pylons sparked, some operators were electrically shocked, and a few stations caught fire. 

The Carrington Event is the most powerful geomagnetic storm on record, and it might be said we dodged a bullet, given it predated the first American power plants by about 20 years. Whereas, in the 1850s, 12,000 miles of telegraph wires crossed the US, at present there are over 5,500,000 miles of power lines. A 2013 paper put forth by researchers at Lloyd's and AER estimates that between 20 and 40 million people in the US are at risk of power outages from a geomagnetic storm similar to the Carrington Event. The extent of outage durations depend on the availability of replacement equipment. It would take at least 5 months to order newly built equipment, likely far longer given the bottleneck of the global logistics crisis. The cost of such a disaster was estimated at $600 billion to $2.6 trillion USD in 2013, equivalent to $800 and $3.4 trillion in 2024. The same paper anticipates similar degrees of solar activity every 100 to 250 years. 

Understanding how the Sun works, how it interacts with geological and human systems, this is the work of heliophysicists, and much of the US-based research is conducted under NASA, meaning that the study of the Sun, at least in the United States, is dependent on the budgetary decisions of Congressional Committee and the Presidency. **The aim of this analysis is to investigate whether the funding of NASA broadly, and the Heliophysics Division specifically, fluctuates in tune with the 11-year cycle of high and low solar activity.** This solar cycle is characterized by periods of magnetic stability and chaos, fully oscillating between the two over 10 to 12 years. The oldest method of measuring solar activity is counting sunspots, darkened areas where magnetic fields are strong enough to suppress heat and energy from reaching the surface. The earliest such observations date back to the 18th century, conducted manually by telescope; though more advanced indicators exist today, like solar radio flux, the longevity of sunspot observations makes a useful metric when doing historical investigations like this one.

By analyzing the relationship between research funding and solar activity, we can gain an understanding of how decision-making processes behind that funding might take the study of solar activity into account. Serious consideration for the effects of solar activity on human development would likely display a positive correlation between solar activity and funding, as there is more data to acquire and process during the window around the solar maximum, and any predictive efforts would be focused on this period as well. Additionally, it's around the solar maximum that the effects of coronal mass ejections are most tangible, and the risk of geomagnetic storm damage most likely, so there may be more lobbying and greater awareness of the need for improved preparedness during this time.


## 2. Hypothesis
State your null and alternative hypotheses clearly and succinctly.

Null:

Alternative:


## 3. Data Description

*Historical NASA Budget Data: Total Budget*, The Planetary Society
* Unit of Analysis: Nominal and inflation-adjusted real budget (in millions USD) of a federal organization wihtin a given government fiscal year
* Description: 132 rows
    - gov_fiscal_year: year from October 1 to September 30
    - president: contemporary sitting president of the United States
    - budget_nominal: yearly appropriation
    - budget_real: yearly appropriation, inflation-adjusted to 2025 value USD
    - budget_real_yearly_delta: change in real budget, year over year
    - inflation_cuml: inflation adjustment value
    - departments_group: "NASA" or "Other"
* Transformations:
    -
    - **TODO**

*Historical NASA Budget Data: NASA Science Divisions Budgets*, The Planetary Society
* Unit of Analysis: Nominal and real budget (in millions USD) of divisions within NASA Science Directorate for a given government fiscal year
* Description: 264 rows
    - gov_fiscal_year: year from October 1 to September 30
    - budget_nominal: yearly appropriation
    - budget_real: yearly appropriation, inflation-adjusted to 2025 value USD
    - budget_real_yearly_delta: change in real budget, year over year
    - division: one of the four primary divisions of NASA Science Directorate, *Planetary Science*, *Astrophysics*, *Heliophysics*, or *Earth Science*
* Transformations:
    -
    - **TODO**

*Sunspot Records*, NOAA Space Weather Prediction Center
* Unit of Analysis: Mean sunspot number, and ancillary values, in a month
* Description: 3323 rows
    - time-tag: YYMMDD of observation
    - ssn: mean number of observed sunspots
    - smoothed_ssn: running average of 'ssn' over several months
    - observed_swpc_ssn: mean observed sunspots, observation conducted by NOAA SWPC
    - smoothed_swpc_ssn: running average of the above over several months
    - f10.7: solar radio flux value
    - smoothed_f10.7: running average of the above
* Transformations:
    - Converted time-tag to datetime datatype
    - 
    - **TODO**


## 4. Methods
Summarize how you analyzed the data:
* The test statistic for your permutation test
* How you simulated or resampled under the null hypothesis
* The metric(s) for which you created bootstrap confidence intervals
* Why the CLT does not apply to at least one metric




## 5. Results
Present your main findings:
* Key summary statistics and visualizations
* Observed test statistic and p-value (if applicable)
* Bootstrap confidence intervals for relevant metrics




## 6. Uncertainty Estimation
Discuss your resampling results:
* How many resamples you used
* What the bootstrap or randomization distributions looked like
* How you interpret the interval estimates




## 7. Limitations
Briefly note any limitations in data, assumptions, or methods, including sources of bias or missing data.

The main limitation of the budget dataset is the lack of controls for external political factors. The inclusion of the 'president' attribute is likely an attempt by the Planetary Society to address this, but it appears insufficient. Military considerations have always been a major factor, if not primary factor, in determing federal allocations to NASA. This is clearly indicated by the massive spike in funding at the beginning of the period, the Space Race of the 1960s, when security concerns and national pride drove the US to compete with the USSR for dominance in space, before tapering off and flattening out following the end of the Apollo program. Extricating the influence of these political factors might be possible, but it would require an in-depth historical investigation outside the scope of this analysis.


## 8. References
List all datasets, tools, libraries, or papers you cited