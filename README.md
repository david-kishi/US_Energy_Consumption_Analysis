# Total Fossil Fuel Energy Consumption and Carbon Dioxide (CO2) Emissions Final Analysis Report

### Description
A basic analysis on Total Fossil Fuel Energy Consumption and CO2 Emissions based on data from [EIA](https://www.eia.gov/opendata/) (U.S. **E**nergy **I**nformation **A**dministration).

### Info / Credits

- Analysis by 
    * `Al San Diego` [@alsandiego](https://github.com/alsandiego)
    * `David Nguyen` [@david-kishi](https://github.com/david-kishi)

- Final Analysis Report written by
    * `David Nguyen` [@david-kishi](https://github.com/david-kishi)

- `REPO:` https://github.com/david-kishi/US_Energy_Consumption_Analysis

- `Analysis Last Updated:` October 14th, 2019

- `Report Last Updated:` October 15th, 2019

*Disclaimer: We are not professional environmental scientists and this is in no way a form of official report.*

### Data Sources
|Name|Type|Description|Website|
|---|---|---|---|
|US Energy Information Administration|API|API Access to US Energy Information Administration. Consists of data on all fuel sources.|https://www.eia.gov/opendata/qb.php|

### Revision History
| # | Description | Author | Version |
|---|---|---|---|
|0|Initial Release|David Nguyen|1.0|

## Table of Contents
- Introduction
    * Why?
    * Types of Energy
- Hypothesis
- Data
- Analysis
    * Total Energy Consumption by State Ranking
    * Total Energy Consumption, by Energy Type, by California & US
    * Total CO2 Emission, by Energy Type, by California & US
    * Total Energy Consumption vs. Total CO2 Emission
    * Total Energy Consumption 2000's Bar Chart
        - CA vs US
    * Total CO2 Emissions 2000's Bar Chart
        - CA vs US
        - US vs NA
        - US vs World
- Conclusion

## Introduction

Hi. We are Al and David, and we're both (at the time this report was written) students at University of California Irvine's Data Analytics Bootcamp. In the last 8 weeks, we have learned skills in `Excel`, `VBA`, `Python`, `Pandas`, `Matplotlib` and `accessing APIs`. In this analysis, we utilized the knowledge we obtained on Python, Pandas, Matplotlib and accessing APIs to perform a basic analysis on data on Fossil Fuel Energy Consumption and CO2 Emissions.

### Why?
We chose Fossil Fuel Energy Consumption and CO2 Emissions as a topic because we were both interested in seeing for ourselves if there was a correlation between the two and it's environmental impact.

The questions we asked ourselves were:
- How is California compared to the rest of the United States?
- How is United States compared to the rest of North America?
- How is United States compared to the rest of the world?
- Is there a correlation between energy consumption and carbon emission?

### Types of Energy
Why are we just covering fossil fuels? According to the US EIA, as of April 2019, fossil fuel make up about 80% of all energy consumptions.

What makes up fossil fuels and their uses?
- Petroleum
    * Transportation and Manufacturing
- Coal
    * Heating, Manufacturing and Electricity
- Natural Gas
    * Manufacturing and Electricity
    
The common fact between all three is that these are **non-renewable energy**. This means that Earth only contains a **finite** amount of fossil fuel. It cannot be replenished unlike renewable energy like solar and wind energy.

## Hypothesis
**H<sub>o</sub>:** As Total Fossil Fuel Energy Consumption increases, CO2 Emissions does **NOT** increase with it.

**H<sub>a</sub>:** As Total Fossil Fuel Energy Consumption increases, CO2 Emissions does increase with it.

## Data
To start analyzing, we'll need some data. We'll need the following:
- Total Fossil Fuel Energy Consumption
    * Total
    * by Petroleum
    * by Coal
    * by Natural Gas
- Total CO2 Emissions
    * Total
    * by Petroleum
    * by Coal
    * by Natural Gas
    
All of the data we were able to retrieve from US EIA's API. https://www.eia.gov/opendata/qb.php?category=371
    
*Note: For Total Fossil Fuel Energy Consumption, we will query for all the states and United States as a whole.*

*Note: For Total CO2 Emissions, we will query for all the states, United States as a whole, North America, and the World.*

## Analysis
### Total Energy Consumption by State Ranking
The first thing we wanted to see was which state had the most total energy consumption.
![TETCB by State Rank](../Images/TETCB_State_Rankings.png)
It's a little hard to see, but that first line at the top is Texas and the second line is California. Let's do a horizontal bar graph and table to narrow it down to the top 5 states with the most recent year in data, 2017.
![TETCB Top 5](../Images/TETCB_Top_5.png)
We also want to see what the total consumption percentage is too through a table.
![TETCB Top 5 Pct Table](../Images/TETCB_Top_5_Table.png)
In 2017, Texas ranked #1 in total energy consumption at a whopping 13,365,864 btu ([british thermal units](https://www.eia.gov/energyexplained/units-and-calculators/british-thermal-units.php)), accounting for 13.687% of the entirety of US's total energy consumption. California trails not far behind, ranking at #2 in total energy consumption at 7,881,348 btu, accounting for 8.071% of US's total energy consumption.

### Total Energy Consumption, by Energy Type, by California & US
Now let's break down the energy types into Petroleum, Coal and Natural Gas to see the trends in California.

![TETCB CA Line Plot](../Images/TETCB_CA_Line_Plot.png)
We can observe in Figure 1 and 2 that in California, Coal is not a widely used source of energy at all. Petroleum is #1 and Natural Gas is #2. Comparing the trends of California and United States, we can see the trends are very similar. California seems to consume about ~10% of what the US does at a time.

Now looking at Figures 3 to 6, we can also deduct that California consumes way over the US average.

### Total CO2 Emission, by Energy Type, by California & US
Now let's break it down in terms of CO2 Emissions.

![CO2 CA Line Plot](../Images/CO2_CA_Line_Plot.png)

We can observe similar trends in CO2 Emissions in California. Petroleum is #1 and Natural Gas #2. Seems we're getting onto something here that we can use towards our hypothesis we made earlier.

An interesting observation we saw looking at the United States plot was that although natural gas is consumed more than coal in the US, CO2 emissions from both are complete opposite. More CO2 commissions come from coal than it does natural gas.

### Total Energy Consumption vs. Total CO2 Emission
Since we see in the previous figures that Energy Consumption and CO2 Emission have similar trends, let's see what happens when we put them against each other in a scatterplot. Is there a correlation or not?

![TETCBvsCO2 State Correlation](../Images/TETCBvsCO2_State_Correlation.png)

The plot above shows each state in it's own separate color. We can clearly see that the top right most in red is Texas with California following shortly below it in purple. (Sorry if the colors are actually not red or purple! I have major color defiency and cannot differiante colors.) It seems to be already clear that there's a trend here as the plots are very close together and uniformly increase, but let's plot a best fit line and find the correlation coefficient just to be sure.

![TETCBvsCO2 Combined State Correlation](../Images/TETCBvsCO2_State_Combined_Correlation.png)

Now we can confidently say there is a strong positive correlation as the correlation coefficient r equals 0.976 with a p-value of 0.0. With a p-value of 0, we can strongly agree with the correlation coefficient of the plot.

Let's look at just California just to see.
![TETCBvsCO2 CA Correlation](../Images/TETCBvsCO2_CA_Correlation.png)

We can see the same strong positive correlation with a correlation coefficient r of 0.925 and a p-value of 2.413E-16, which is practically 0.

### Total Energy Consumption 2000's Bar Chart
#### CA vs US
![TETCB 2000s CA vs US](../Images/TETCB_CA_vs_US_Bar_2000.png)

### Total CO2 Emission 2000's Bar Chart
#### CA vs US
![CO2 2000s CA vs US](../Images/CO2_CA_vs_US_Bar_2000.png)

#### US vs North America
![CO2 2000s US vs NA](../Images/CO2_US_vs_NA_Bar_2000.png)

#### US vs World
![CO2 2000s US vs World](../Images/CO2_US_vs_World_Bar_2000.png)

## Conclusion
For reference, here are the hypotheses once again.

**H<sub>o</sub>:** As Total Fossil Fuel Energy Consumption increases, CO2 Emissions does NOT increase with it.

**H<sub>a</sub>:** As Total Fossil Fuel Energy Consumption increases, CO2 Emissions does increase with it.

Based on our analysis, we can reject the null hypothesis `As Total Fossil Fuel Energy Consumption increases, CO2 Emissions does NOT increase with it`. This hypothesis was disproven with our correlation scatter plot of Total Fossil Fuel Energy Consumption vs. CO2 Emissions.
![TETCB vs. CO2 Correlation](../Images/TETCBvsCO2_State_Combined_Correlation.png)
With such a strong positive correlation seen above (correlation coefficient of 0.976, p-value of 0.0), we can conclude that there is a correlation between fossil fuel energy consumption and CO2 emissions. `As Total Fossil Fuel Energy Consumption increases, CO2 Emissions increases with it.`