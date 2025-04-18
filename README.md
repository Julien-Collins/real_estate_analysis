# 🏡 Real Estate Market Analysis – Simulated MLS Insights

This project simulates a real estate market using a synthetic dataset modeled after MLS property listings. It includes over 1,000 property records across two fictional counties and 24 made-up cities. The goal is to analyze pricing dynamics, competitiveness, tax assessments, and listing characteristics using SQL within a PostgreSQL environment.

This end-to-end project demonstrates real-world data analytics workflow—covering data generation, relational database design, SQL querying, and interpretation of insights. It’s designed with the kind of work analysts perform at PropTech companies like **Redfin**, **Opendoor**, or **Zillow** in mind.

---

## 🧭 Project Overview

- **🔧 Synthetic Data Generation**  
  Generated 1,000+ listings using Python (`Faker`, `Pandas`), including home prices, specs, days on market, and property taxes.

- **🏗️ Database Design & Implementation**  
  Structured data into normalized tables and implemented the schema in **PostgreSQL** via **pgAdmin**.

- **🧠 SQL-Driven Analysis**  
  Executed a series of analytical SQL queries to uncover market trends and pricing behaviors.

- **🎯 Business Context**  
  The insights support potential homebuyers, real estate investors, or data teams in identifying undervalued markets, overpricing, and market speed.

---

## 🛠 Tools Used

- **Python** – Data generation using `Faker`, dataframes via `Pandas`
- **PostgreSQL / pgAdmin** – Database creation and SQL analysis
- **SQL** – For exploration, transformation, and market queries

---

## 🗃️ Dataset Features

The generated dataset includes the following attributes:

- Property Specs: Bedrooms, Bathrooms, Square Footage, Lot Size  
- Location: Street Address, City, State, Zip  
- Financials: Original List Price, Selling Price, Tax Rate, Annual Property Tax  
- Performance: Days on Market (CDOM), Price per Sq Ft

##🔎Key SQL Queries & Insights

##📊Query 1: How Expensive is Each Square Foot?
<br>

- To begin my analysis, I pulled the average price per square foot of all sold homes to get an idea of the overall pricing landscape:

<br> 

![Avg Price Per Sqft](./avg-price-persqft-Screenshot%202025-04-17%20112643.png)

<br>

##🏙️Query 2: Top Cities by Avg Home Sales Price

<br>

- I then pulled the average price of home, grouping each sold home into their respective city.:

<br>

![RealReal Avg per City](./realrealavgpercity-Screenshot%202025-04-17%20111835.png)

<br>

- As demonstrated in the data, the average sold price is north of $700k for the top 10 cities, with one city being above $2 million.
- Evidently, that city had far fewer sales than the others in the table, rendering the data less statistically significant compared to the rest of the set.
- A WHERE clause ensuring the number of solds was above a certain number of sales would have eliminated the outlier.

<br>

##🧱Query 3: AVG Property Specs by City 
<br> 

- Now, knowing the average price ranges, I created a query to evaluate the average specs for homes per city.
- Doing this, one can gather an idea on the average home available by city.
- You can also cross-evaluate it against the avg price per home per city, or the avg price per sq ft.
  
<br>

![Avg Specs per City](./avg_specs_percity_Screenshot%202025-04-17%20113838.png)

##⏳Query 4: CDOM (Days on Market)
<br>

- Next, I pulled the average consecutive days on market (CDOM) per city with the parameter that each city had over 30 sales during the 6 month span.
- This 30-sale parameter eliminates outliers.
- This provides a full-circle look at how fast or slow inventory is moving in any particular market. 

<br>

![CDOM Over 30 Sales](./cdom-over30sales-Screenshot%202025-04-17%20112726.png)

<br>

##🧾Query 5: Original List Price vs Selling Price
<br>

- To assess the market further, I found the total dollar amount and percentage difference between the original listing price and the actual selling price (of that same home) and grouped by city.
- This query explores the market dynamics of each city. If the selling price is well under the original listing price, it suggests the market is cooling; if it is much higher, then it indicates a hot market.
- Understanding this relationship provides insight into how one can negotiate in a market, and the overacrching housing economic conditions.

<br>

![Percentage Real Over Ask](./percentagerealoverask-Screenshot%202025-04-18%20113125.png)


<br>

- As you can see, every result indicates the homes are selling for under the original asking price.
- Given the statistically significant transaction total of Josephhaven, Port Pamela, Duketon, and North Lance, we can look at those price differences to get a better gauge for the overall market.
- Most homes are selling within 3-4.5% under ask.

##💰Query 6: Are Homeowners Overpaying in Property Taxes?
<br> 

- Here, I utilize a query to breakdown the avgerage annual tax rates on these fake homes against real tax data I gathered on county assessor sites.
- This will shed light on the accuracy of the property tax assessed value compared to the selling price, and provide the difference between the two.
- Oftentimes, home owners or consumers want to know if their assessed value is higher than actual market, so as to determine if they're being over taxed.

<br>

![Tax Rates Diff Actual vs Projected](./taxrates_diffactual%20vs%20projected-Screenshot%202025-04-17%20115540.png)

<br>

- The median tax rate in the data reflects county assesor tax rates in WA. The projected annual property tax is then derived by multiplying that number by avg selling price
- I then took the "actual" (fake taxes generated) avg and compared the difference.
- It turns out that the avg "actual" taxes is well under the projected tax totals based on real figures, suggesting homeowners on average are not being over taxed.
- I created a fake tax rate table and joined with the main re table to perform this.

<br>


##  Final Takeaways

- Homes across most cities are selling **below asking**, indicating a **buyer’s market**.
- The average **Consecutive Days on Market (CDOM)** suggests homes are spending **~45 days** on the market before selling.
- The **price per square foot** in most cities falls within the **$300–$400** range.
- Property tax rates in the dataset are **lower than real county averages**, implying that homeowners may be **under-assessed**.



##  Future Enhancements

-  **Integrate mortgage data** to analyze monthly payment scenarios and affordability trends by city.
-  **Add time-series analysis** to observe how listing prices, DOM, and sell-to-list ratios shift **month over month**.
-  **Create visual dashboards** using tools like **Tableau** or **Power BI** for a more interactive, client-ready experience.
-  **Incorporate school district ratings** or **local crime data** to offer more granular neighborhood-level insights.
-  **Use machine learning models** to predict home prices or DOM based on features like size, location, and condition.


## 👀 Why It Matters

This project reflects the skills needed in a real PropTech analyst role—cleaning and modeling messy data, running performant SQL, and deriving insights that impact pricing, market targeting, and customer-facing dashboards. 


