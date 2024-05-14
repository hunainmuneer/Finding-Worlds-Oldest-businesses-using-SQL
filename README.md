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

## Key Findings

1. **1. The oldest business in the world:**
SELECT S.customer_id, SUM(M.price) AS total_amnt
FROM sales S
JOIN menu M ON S.product_id = M.product_id
GROUP BY S.customer_id
ORDER BY customer_id
2. **Businesses Before 1000:**
   - Six businesses in the dataset were founded before 1000, with the oldest dating back to 578.

3. **Categories and Detail:**
   - Categories of these businesses were explored, providing a detailed look at the types of enterprises that endured for over a millennium.

4. **Common Business Categories:**
   - "Banking & Finance" is the most common category among the oldest businesses globally.

5. **Oldest Business by Continent:**
   - The oldest businesses on each continent were identified, revealing historical trends and timelines.

6. **Comprehensive Dataset:**
   - Tables were joined to create a comprehensive dataset for more in-depth analysis, combining information on the business, founding year, category, country, and continent.

7. **Categories by Continent:**
   - Counts of businesses in each continent and category were examined, shedding light on the distribution of business types across different regions.

8. **Filtered Results:**
   - The analysis was refined to focus on continent/category pairs with a count greater than 5, providing a more manageable view of significant trends.
