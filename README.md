# What and Where are the World's Oldest Businesses

![](400px-Eingang_zum_St._Peter_Stiftskeller.jpg)

Image: St. Peter Stiftskeller, founded 803. Credit: [Pakeha](https://commons.wikimedia.org/wiki/File:Eingang_zum_St._Peter_Stiftskeller.jpg)

## Description

- An important part of business is planning for the future and ensuring that the business survives changing market conditions.
- Some businesses do this remarkably well and last for hundreds of years. BusinessFinancing.co.uk [researched](https://businessfinancing.co.uk/the-oldest-company-in-almost-every-country/) the oldest company that is still in business in (almost) every country and compiled the results into a dataset.
- In this project, we will explore data from BusinessFinancing.co.uk on the world's oldest businesses: when were they founded, and which industries do they belong to?

## Data

### `categories` table

| Column | Definition | Data Type |
|-|-|-|  
|category_code| Code for the category of the business |`varchar`|
|category| Description of the business category |`varchar`|

### `countries` table

| Column | Definition | Data Type |
|-|-|-|
|country_code| ISO 3166-1 3-letter country code |`varchar`|
|country| Name of the country |`varchar`|
|continent| Name of the continent that the country exists in |`varchar`|


### `businesses` table

| Column | Definition | Data Type |
|-|-|-|
|business| Name of the business |`varchar`|  
|year_founded| Year the business was founded |`int`|
|category_code| Code for the category of the business |`varchar`|
|country_code| ISO 3166-1 3-letter country code |`char`|

## Problem statement and Key Findings

1. **1. The oldest business in the world:**
```sql
SELECT MIN(year_founded) AS min, MAX(year_founded) AS max
FROM businesses
```
- Answer:
  
| min | max |
|-|-|
|578|1999|

- The SQL query uses aggregate functions to find range of the founding years of the business in the `businesses` dataset.
- The oldest business in the world was founded in the year 578. 

2. **How many businesses were founded before 1000?**
```sql
SELECT COUNT(*)
FROM businesses
WHERE year_founded < 1000
```
- Answer:
| count | 
|-|
|6|

- The SQL query filters out the number of businesses that were founded before th year 1000.
- Six businesses in the dataset were founded before 1000, with the oldest dating back to 578.

3. **Which businesses were founded before 1000?:**
```sql
SELECT *
FROM businesses
WHERE year_founded < 1000
ORDER BY year_founded ASC
```
- Answer:
| business | year_founded | category_code | country_code |
|-|-|-|-|
|Kongō Gumi	| 578 | CAT6 | JPN |
|St. Peter Stifts Kulinarium	| 803 | CAT4 | AUT |
|Staffelter Hof Winery	| 862 | CAT9 | DEU |
|Monnaie de Paris| 864 | CAT12 | FRA |
|The Royal Mint| 886 | CAT12 | GBR |
|Sean's Bar| 900 | CAT4 | IRL |

- The SQL query finds more details about the 6 businesses that were founded before the year 1000.
- The result shows the business name, the year it was founded, the code of the industry it operates in and the country it was founded in.
- The world's oldest business still operating today is in Japan.

5. **Common Business Categories:**
   - "Banking & Finance" is the most common category among the oldest businesses globally.

6. **Oldest Business by Continent:**
   - The oldest businesses on each continent were identified, revealing historical trends and timelines.

7. **Comprehensive Dataset:**
   - Tables were joined to create a comprehensive dataset for more in-depth analysis, combining information on the business, founding year, category, country, and continent.

8. **Categories by Continent:**
   - Counts of businesses in each continent and category were examined, shedding light on the distribution of business types across different regions.

9. **Filtered Results:**
   - The analysis was refined to focus on continent/category pairs with a count greater than 5, providing a more manageable view of significant trends.
