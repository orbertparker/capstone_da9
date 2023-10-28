# Poverty and Pollution in Tennessee

## Table of Contents
* [Motivation](#motivation)
* [Technologies](#technologies)
* [Data Process](#dataprocess)
* [Findings](#findings)

## Motivation

#### Poverty and Pollution in Tennessee aims to examine the effects of lead exposure on the people of Tennesse, and identify any disparities in the quality-of-life and effectiveness of government intervention between high-risk and low-risk counties.

#### This deep dive with a chance encounter with an old friend at the hardware store. We were catching up and I mentioned that I had just recently purchased my first home in an area of Chattanooga called East Lake, at which point he told me that the neighborhood I lived in was part of something called a "Superfund site" and that I should ask the EPA to come out and test my soil for lead. I filed the request as soon as I got home, and then spent the next several absorbing every piece of information I could find about lead and the consequences of lead exposure.

#### I learned about the ubiquity of lead-use all throughout human history, particularly in the 19th and 20th centuries, and the terrible effects even the smallest levels of exposure can have on the body. It's especially disasterous for children, for whom both prenatal and postpartum exposure can lead to behavior problems, lower IQ, cognitive dysfunction, hearing loss, and even death. Knowing our country's history of class inequality and redlining, I've long suspected that East Lake isn't the only low-income area of Tennessee being under-served in the area of lead mitigation and abatement and I was eager for the opportunity to analyze the data in order to find out.

## Technologies

#### The vast majority of my analysis was completed in Excel and Tableau, with some additional analysis of the distribution of EPA Superfund sites completed using Python 3 and Jupyter Noterbook. All maps were produced within Tableau, and the final presentation was completed in PowerPoint.

## Data Process

#### The key metric of my analysis was the EBLL, or Elevated Blood Lead Levels, of children in Tennessee. As part of the Childhood Lead Poisonig Prevention Program, the Tennessee Department of Health performs blood lead level testing every year for a selection of children under 6 in all 95 Tennessee counties. When an EBLL meeting or exceeding 5 micrograms of lead per deciliter of blood, it's logged in the DOH's own internal database in addition to the CDC and The University of Tennessee's LeadTRK system.

#### The most recent 5 years of EBLL data are publicly viewable on the TNDOH's surveillance dashboard (https://www.tn.gov/health/health-program-areas/fhw/tn-clpp.html). The embedded web app used to power the dashboard made it impossible to scrape the data, but I was able to slowly and surely extract the information I needed by using the "Get Data From Picture" function in Excel. After some significant manual correction, I had EBLL data for 88 of Tennessee's 95 counties. From there, I found the average EBLL during the time frame reported for each county and created two groups: the top 10 counties in terms of highest EBLL and the top 10 counties in terms of lowest EBLL.

To compare the quality-of-life for each groups, I used the extensive data available from the US Census Bureau's American Community Survey (https://www.census.gov/programs-surveys/acs). The ACS is a persistent and on-going program of surveys and analysis that releases their latest and greatest findings yearly. The data can be drilled down to the county level, and every 5 years they release a dataset of the averages over the corresponding time period, so it was a perfect match for my project. The biggest challenge here was navigating the overwhelming amount of information available, but fortunately the bureau provides an online table building tool (https://data.census.gov/).

Data for the Deteriorated Paint Index (DPI) is available from the federal Department of Housing and Urban Development (https://hudgis-hud.opendata.arcgis.com/datasets/HUD::deteriorated-paint-index-by-county/about) and information about currently active Superfund sites is available from the EPA (https://www.epa.gov/superfund/search-superfund-sites-where-you-live).

## Findings

#### Unsurprisingly, counties with higher EBLL fared far worse in a variety of quality-of-life metrics, including infant mortality, rates of cognitive disabilities, and rates of hearing loss. But when I compared the rates of DPI and the percentage of homes built before 1979 (lead paint was banned in 1978), I found that there wasn't a very big disparity between the two county groups. Therefore, the greatest access point for lead in the community must come from unremediated sites of lead contamination, such as old factories, foundries, and mines. To further illustrate this point, I examined the history of the worst performing county (Hancock) and if any efforts had been made to deal with the lead left behind from 20 years of mining operations. I found none, and to see if similar efforts to remediate contaminated sites for the rest of Tennessee had been completed, I mapped the location of all currently active and found that the overwhelming number of them were located in the best performing counties.


## Conclusion

#### The harm caused by lead exposure is extremely well documented, and it's clear from the data that the worst performing counties have been neglected by the federal government. Since the process of establishing a Superfund site can only be initiated by some sort of municipal authority, my recommendation is that communities take the initiative to perform their own soil testing that can then be reported to their local Department of Housing and push their represenatives to alert the EPA should a pattern of contamination be discovered.