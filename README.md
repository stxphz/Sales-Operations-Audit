
## Project Description

As a data analyst at TTWC Consulting Agency (<i>TripleTen World Consultancy Consulting Agency</i>), they have assigned a significant project involving a special client: AtliQ Hardware. They are a leading computer hardware producer operating across India and have expanded internationally as well. AtliQ Hardware has asked TTWC Consulting Agency to conduct a comprehensive audit of their sales operations and to implement automation measures for their existing data processes.

The client is interested in three key business domains:

1. Financial Analysis: This entails researching revenue, profits, and margin fluctuations over time, analyzing market trends, and identifying the most profitable product categories.

2. Product Analysis: This involves identifying top-selling items, strategizing methods to enhance sales performance, and examining changes in product popularity across different time frames and markets.

3. Customer Analysis: This segment focuses on customer segmentation, understanding purchasing behaviors, and devising strategies to optimize business relationships.

The objective is to delve into these areas, gather relevant data, and develop insightful dashboards for AtliQ Hardware's future reference.

As the analyst, we are assigned the responsibility of selecting one of the three research domains that piques interest and to develop a comprehensive research plan accordingly. For this project, collaboration with a team leader and peers is encouraged to ensure a thorough examination of all options.

AtliQ Hardware has provided a SQLite database backup for the analysis. Utilization of various tables within the database is permitted. However, access is restricted solely to database connections; CSV files are not provided, and the loading of the entire database into CSV format is prohibited by the company.

<br>

## Data Dictionary

The <code>dim-customer</code> contains customer-related data

- <code>customer_code</code>: unique identifier of customer. One customer can have several customer_codes.
- <code>customer</code>: company name of customer
- <code>platform</code>: platform through which the sale's been done. Customer should have one platform.
- <code>channel</code>: channel of sale. Customer may have several channels.
- <code>market</code>: country of the customer's office
- <code>sub_zone</code>: abbreviation of the region. For one market there should be one sub_zone.
- <code>region</code>: region of the customer's office. For one market there should be one region.

<br>

The <code>dim-product</code> contains product-related data

- <code>product_code</code>: unique indentifier of product
- <code>division</code>: group of the product
- <code>segment</code>: type of the product (the sub-division)
- <code>category</code>: category of the product
- <code>product</code>: full name of the product
- <code>variant</code>: variant of the product

<br>

The <code>fact_gross_price</code> contains gross price information for each product

- <code>product_code</code>: unique indentifier of product
- <code>fiscal_year</code>: year of transaction
- <code>gross_price</code>: final price for the product

<br>

The <code>fact_manufacturing_cost</code> contains the cost incurred in the production of each product

- <code>product_code</code>: unique identifier of product
- <code>cost_year</code>: year of production
- <code>manufacturing_cost</code>: cost of production of unit of product

<br>

The <code>fact_pre_discount</code> contains pre-invoice deductions information for each product

- <code>customer_code</code>: unique identifier of customer
- <code>fiscal_year</code>: year when discount was valid
- <code>pre_invoice_discount_pct</code>: discount % per invoice for specific customer

<br>

The <code>fact_sales_monthly</code> contains monthly sales data for each product

- <code>date</code>: date of transaction
- <code>product_code</code>: unique identifier of product
- <code>customer_code</code>: unique identifier of customer
- <code>sold_quantity</code>: sold items to customer on that date
- <code>fiscal_year</code>: year of transaction
