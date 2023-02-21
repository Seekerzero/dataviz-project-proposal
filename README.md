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



## Prototypes

I’ve created a proof of concept visualization of this data. In the picture below, it shows the top 10 countries that have most vaccinated person in the world.

[![image](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/vaccine.png)]([https://vizhub.com/Seekerzero/661e60f4405d4a29ac2d1808692a287c](https://vizhub.com/Seekerzero/661e60f4405d4a29ac2d1808692a287c?edit=files&file=viz.js))

```
[![image](https://raw.githubusercontent.com/Seekerzero/dataviz-project-proposal/master/vaccine.jpg)]([https://vizhub.com/Seekerzero/661e60f4405d4a29ac2d1808692a287c](https://vizhub.com/Seekerzero/661e60f4405d4a29ac2d1808692a287c?edit=files&file=viz.js))
```

## Questions & Tasks

The following tasks and questions will drive the visualization and interaction decisions for this project:

 * which country has largest number of vaccinated population and its vaccination types?
 * which country has largest number of vaccinated first dose population and its vaccination types.
 * which country has largest number of vaccinated second dose population and its vaccination types.
 * what is the largest number of vaccine dose type and it vaccinated distribution of countries.

## Sketches

![image-20230220204533373](C:\Users\Seeker\Desktop\dataviz-project-proposal\vaccine output.png)

This sketch introduces how different types of vaccines being sold (transferred) in the world. The purple one represents the producer (country), where the curves connect to a different country that the vaccine gets to. Different colors of curves represent different vaccine.

![image-20230220204926460](https://github.com/Seekerzero/dataviz-project-proposal/blob/master/vaccine%20population.png)

This sketch introduces the proportion of vaccinated population in each country. the percentage of color filled represent the proportion. Different color can represent different types of doses.

## Open Questions

- A appropriate API for globe visualization
- Transition between different visualization graph. (Interaction)

## Milestones

- Week 7&8(9): Get the globe out and map the data into each region.
- Week 9: Get the population viz done.
- Week 10:Create interaction for different regions.
- Week 11: Vaccine Transfer viz starts
- Week 12: Animation on the viz.
- Week 13: Transition between viz.
- Week 14: Refine the work, packaging
