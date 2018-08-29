# Retail Prices of Key Commodities in India
Considering that the dataset contains the prices of various commodities from the year 1997 to 2015.

## Code
A Kaggle kernel was used for the development to skip over the installation processes as well as overcome hardware capability restrictions.
The link to the kernel:
https://www.kaggle.com/prerna237/india-retail-eda

## Preliminary Observations
These are some observations about the various columns in the dataset:
* **Date** : The date values were at a 'day' level granularity meaning (DD/MM/YYYY).
* **Centre** : One of the 75 regional centres where the prices are recorded
* **Commodity** : The prices of the following commodities were listed: 
-- Tur/Arhar Dal
-- Tomato 
-- Tea Loose
-- Sunflower Oil (Packed)
-- Sugar
-- Salt Pack (Iodised)
-- Onion
-- Milk
-- Rice
* **Price_per_Kg**: Price per Kilogram of the item with values as low as 1 Re to as high as Rs 1050.
* **Region**: The region of the country the centre belongs to.
* **Country**: The dataset had values only from India.

## Data Exploration
The aim was to answer the following questions by analyzing the available data:
1. Which commodity has shown the steepest price growth over the years?
2. Which centre in the country has the highest cost of living?
3. Are certain commodities more expensive during certain months of the year?
4. Which factor( Date, location, commodity type, etc) plays the most prominent factor in the pricing?


## Insights
The insights gathered during the analysis of the data to answer the above questions have been summarized below:
##### Inflation rate for commodities:
To visualize which commodity had the steepest price growth over the years, a line plot of the Price per Kg of the commodity for each year was created. From these line plots, it is visible that 'Tea Loose' had the steepest price growth
However, an alternative to derive this insight was a bar graph of the % change in the commodity's price from 1997 to 2015. This graph too gave the same results.
_Tea Loose had the steepest price growth followed by Sunflower Oil and then by Tur/Arhar dal._
##### Cost of living across centres in the country:
For this question, a metric _Cost_of_living_ was defined as the total cost of key commodities i.e if the data was something of the following form, then 
_Cost_of_living_ = 30.0 + 25.0 + 12.0 = Rs 67.00 
| Commodity        | Price per Kg|
| ------------- |:-------------:|
| Tea Loose | 30.0 |
| Rice    | 25.0      |
| Tomato | 12.0      |

However, it is necessary to note that the data for the price of every commodity in every year in every centre may not be available. 
More so, once the data was mined to extract the relevant fields, it was found that
most centres had the prices of only two commodities for a particular year. For example, Shillong had the prices of only Onion and Rice in the year 1997. 
_As there wasnt any consistency in the manner in which this data was present, any further calculation or derivation of insight from the same would have been spurious._

##### Correlation between Prices of commodities with Months of the year:
There is often a correlation between the time of year and the price of commodities. Mangoes for example would be comparitively cheaper during the months of May, June and July than the rest of the months.
To look for such trends, a bar plot of the avg prices of each commodity during each month was plotted.


##### Factors influencing prices of commodities:
To understand which factors played a major role in deciding the prices , the dataset was further decomposed so that the set of columns were now as follows:
* Year
* Month
* Day
* Commodity
* Centre
* Region

Moreover since we were dealing solely with the prices in India, the 'Country' column was dropped.
