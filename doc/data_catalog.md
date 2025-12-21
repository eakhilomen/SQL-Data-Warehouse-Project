Data Dictionary for Gold layer
OverView
The Gold layer is the business-level data representation , structured to support analytics and reporting use cases. it consists of dimension tables and fact tables for specific business metrics
------------------------------------------------------------------------------------------------------------------------------------------------------
1.** gold.dim_customers**
. Purpose: Store customer details enriched with demographic and geographic data
. Colunms :

| Column Name      | Data Type      | Description |
|------------------|----------------|-------------|
| customer_key     | INT            | Surrogate key uniquely identifying each customer. |
| customer_id      | INT            | Unique numerical identifier for the customer. |
| customer_number  | NVARCHAR(50)   | Alphanumeric customer code used for tracking. |
| first_name       | NVARCHAR(50)   | Customer's first name. |
| last_name        | NVARCHAR(50)   | Customer's last name. |
| country          | NVARCHAR(50)   | Country of residence. |
| marital_status   | NVARCHAR(50)   | Marital status (‘Married’, ‘Single’). |
| gender           | NVARCHAR(50)   | Gender (‘Male’, ‘Female’, ‘n/a’). |
| birthdate        | DATE           | Date of birth (YYYY-MM-DD). |
| create_date      | DATE           | Date when the customer record was created. |

