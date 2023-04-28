# Data Visualization Project

## Data

The data I propose to visualize for my project is World Vaccination Data from WHO.

Source: https://covid19.who.int/data https://covid19.who.int/who-data/vaccination-data.csv

The dataset is group by country, which shows vaccinated population and vaccine dose type in each country.

- categorical: COUNTRY	String	Country, territory, area.
- categorical: ISO3	String	ISO Alpha-3 country code.
- categorical: WHO_REGION	String	WHO regional offices: WHO Member States  are grouped into six WHO regions: Regional Office for Africa (AFRO),  Regional Office for the Americas (AMRO), Regional Office for South-East  Asia (SEARO), Regional Office for Europe (EURO), Regional Office for the Eastern Mediterranean (EMRO), and Regional Office for the Western  Pacific (WPRO).
- categorical: DATA_SOURCE	String	Indicates data source: - REPORTING: Data reported by Member States, or sourced from official reports - OWID:  Data sourced from Our World in Data: https://ourworldindata.org/covid-vaccinations.
- quantitative: DATE_UPDATED	Date	Date of last update.
- quantitative: TOTAL_VACCINATIONS	Integer	Cumulative total vaccine doses administered.
- quantitative: PERSONS_VACCINATED_1PLUS_DOSE	Decimal	Cumulative number of persons vaccinated with at least one dose.
- quantitative: TOTAL_VACCINATIONS_PER100	Integer	Cumulative total vaccine doses administered per 100 population.
- quantitative: PERSONS_VACCINATED_1PLUS_DOSE_PER100	Decimal	Cumulative  persons vaccinated with at least one dose per 100 population.
-  quantitative: PERSONS_FULLY_VACCINATED	Integer	Cumulative number of persons fully vaccinated.
- quantitative: PERSONS_FULLY_VACCINATED_PER100	Decimal	Cumulative number of persons fully vaccinated per 100 population.
- categorical: VACCINES_USED	String	Combined short name of vaccine: “Company - Product name” (see below).
- quantitative: FIRST_VACCINE_DATE	Date	Date of first vaccinations.  Equivalent to start/launch date of the first vaccine administered in a  country.
-  quantitative: NUMBER_VACCINES_TYPES_USED	Integer	Number of vaccine types used per country, territory, area.
- quantitative: PERSONS_BOOSTER_ADD_DOSE	Integer	Persons received booster or additional dose.
- quantitative: PERSONS_BOOSTER_ADD_DOSE_PER100	Decimal	Persons received booster or additional dose per 100 population.

## Questions & Tasks

The following tasks and questions will drive the visualization and interaction decisions for this project:

 * which country has largest number of vaccinated population and its vaccination types?
 * which country has largest number of vaccinated first dose population and its vaccination types.
 * which country has largest number of vaccinated second dose population and its vaccination types.
 * what is the largest number of vaccine dose type and it vaccinated distribution of countries.

## Prototypes

I’ve created a proof of concept visualization of this data. In the picture below, it shows the top 10 countries that have most vaccinated person in the world.

[![image](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/vaccine.png)]([https://vizhub.com/Seekerzero/661e60f4405d4a29ac2d1808692a287c](https://vizhub.com/Seekerzero/661e60f4405d4a29ac2d1808692a287c?edit=files&file=viz.js))

([https://vizhub.com/Seekerzero/ecd57281d8a74c9192db54085e9753af](https://vizhub.com/Seekerzero/ecd57281d8a74c9192db54085e9753af?edit=files&file=index.html))
```
[![image](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/vaccine.jpg)]([https://vizhub.com/Seekerzero/661e60f4405d4a29ac2d1808692a287c](https://vizhub.com/Seekerzero/661e60f4405d4a29ac2d1808692a287c?edit=files&file=viz.js))
```

## Sketches

![image](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/vaccine%20population.png)

This sketch introduces the proportion of vaccinated population in each country. the percentage of color filled represent the proportion. Different color can represent different types of doses.

## Open Questions

- A appropriate API for globe visualization
- Transition between different visualization graph. (Interaction)

## Planning Milestones

- Week 7&8(9): Get the globe out and map the data into each region.
- Week 9: Get the population viz done.
- Week 10: Create interaction for different regions.
- Week 11: Vaccine Transfer viz starts
- Week 12: Animation on the viz.
- Week 13: Transition between viz.

- Week 14: Refine the work, packaging



## Implementation

### First Implementation:

[First Implementation](https://vizhub.com/Seekerzero/56fd93d1c4e24f47aa756e3b50b6d611?edit=files&file=index.html)

#### Features achieved:

At the first implementation, I map the data into playing globe template from the [vizhub](https://vizhub.com/aishwarya8615/f44704d93554421a828fa7f23a11371c) . Using this template, I successfully load the total vaccination number, vaccinated portion from the dataset, also load the population growth of 2022 for each country into the template to replace the original old one. Where the each data could be switched by toggle to button on the right hand side. This template also include the feature that allows user to see the data value when the mouse is hover on the globe. The following are the pictures for the different data load:
Total Vaccination on globe:

![](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/pics/final_p1.png)

Vaccinated Portion on globe:

![](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/pics/final_p2.png)

Population Growth on globe:

![](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/pics/final_p3.png)

Also the globe could be also transform to a map, here is one of the examples:

Population Growth on map:

![](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/pics/final_p4.png)

The template can also transform the data value into a scatter plot which the reference axis is the country GDP. In this implementation, I also replace the data to a 2022 newer data. Here is one of the examples:

Total Vaccination shot data in a diagram:

![](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/pics/final_p5.png)



#### Problem of the first template:

While the template have already setup the logic for transformation between each data, it contains several drawbacks:

1. The code is based on old html version. Most of the code were written inside the index.html, which makes the code hard to edit and customize.
2. All the data has to be retrieved one by one, since the state machine is based on dataset-wise switching. It is hard to edit the structure into the attribute based switching. So I have to convert the existing dataset into several smaller one, where all of them has to map with the country iso3 code first.
3. The diagram does not make sense and also the globe is not necessary for the data reading. Even though the diagram is implemented, it does not make sense to map the data correlated to gdp, which is hard make any explanation. Also even the globe looks cool, but it actually affect the visualization efficiency.

### Second Implementation:

[Second Implementation](https://vizhub.com/Seekerzero/2da939c6f5af4d84aa5f464a8556bab0?edit=files)

Given the experience from the first implementation. I develop a new scripts that allows better maintenance and visualize performance. And its original from the lecture template that Professor Kelleher provided from the course ([origInal template](https://vizhub.com/curran/f2199edb602a4a28af5f797381eca5d5)). Where in this implementation, I use a drop down menu to change the data source and also use a the toggle button to switch between the data map to a bar chart which shows the top 10 country in this data. The drop down menu works in the both states either in the map and in the bar chart. Where inside the bar chart, each bar use different color, also the data value is shown on the top of the bar.

The following are the pictures show this implementation:

The map for vaccinated portion:

![](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/pics/final_p6.png)

The map for fully vaccinated population:

![](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/pics/final_p7.png)

The bar chart:

![](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/pics/final_p8.png)





## Future work

1. Adding time scale to change the data based on the date.
2. More interaction, especially include multi data show together inside the one chart.

​                                                                                             
