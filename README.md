# Real Estate Analysis

This project demonstrates the use of a synthetic real estate dataset to simulate MLS-style property listings for 2 made up counties and 24 fake cities. It involves data generation, database design, and analysis, all implemented using SQL in PostgreSQL. The project showcases SQL queries for real estate analysis, including property sales trends, price per square foot, and tax rate comparisons over a 6 month period. 

## Project Overview

- **Synthetic Data Generation:** Used Python (Faker) to generate 1,000+ synthetic property listings, including property prices, locations, architectural styles, and transaction details.
- **Database Implementation:** Designed and implemented a PostgreSQL database in pgAdmin, where data was imported and structured into tables.
- **SQL Analysis:** Performed a series of analyses using SQL queries to answer key questions about the real estate market.

## Tools Used

- **Python (Faker, Pandas)** – For generating synthetic property listings.
- **PostgreSQL / pgAdmin** – For database implementation and SQL query execution.
- **SQL** – For data exploration, transformation, and analysis.

## Data Generation

The dataset contains over 1,000 property listings with details such as:

- Listing Number
- Property Address (Street, City, State, Zip Code)
- Property Features (Price, Bedrooms, Bathrooms, Square Footage, Lot Size)
- Sale Information (Original Price, Selling Price, Days on Market, etc.)
- Property Tax Data (Annual Taxes, Tax Rate)

A Python script was used to generate this data:
![Script Snippet](fake_data_python_new.png)

## Sample Analysis
<br>

**In this section, I pair my knowledge of real estate with my data analytic skills to assess various metrics related to the market at-large.**
<br>

## Query 1:
<br>

- To begin my analysis, I pulled the average price per square foot of all sold homes to get an idea of the overall pricing landscape:

<br> 

![Avg Price Per Sqft](./avg-price-persqft-Screenshot%202025-04-17%20112643.png)

<br>

## Query 2:

<br>

- I then pulled the average price of home, grouping each sold home into their respective city.:

<br>

![RealReal Avg per City](./realrealavgpercity-Screenshot%202025-04-17%20111835.png)

<br>

- As demonstrated in the data, the average sold price is north of $700k for the top 10 cities, with one city being above $2 million.
- Evidently, that city had far fewer sales than the others in the table, rendering the data less statistically significant compared to the rest of the set.
- A WHERE clause ensuring the number of solds was above a certain number of sales would have eliminated the outlier.

<br>

## Query 3: 
<br> 

- Now, knowing the average price ranges, I created a query to evaluate the average specs for homes per city.
- Doing this, one can gather an idea on the average home available by city.
- You can also cross-evaluate it against the avg price per home per city, or the avg price per sq ft.
  
<br>

![Avg Specs per City](./avg_specs_percity_Screenshot%202025-04-17%20113838.png)







