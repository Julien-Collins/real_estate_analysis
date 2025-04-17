# Real Estate Analysis - 6 months

This project demonstrates the use of a synthetic real estate dataset to simulate MLS-style property listings. It involves data generation, database design, and analysis, all implemented using SQL in PostgreSQL. The project showcases SQL queries for real estate analysis, including property sales trends, price per square foot, and tax rate comparisons.

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

