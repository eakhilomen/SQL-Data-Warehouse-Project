Data Dictionary for Gold layer
OverView
The Gold layer is the business-level data representation , structured to support analytics and reporting use cases. it consists of dimension tables and fact tables for specific business metrics
------------------------------------------------------------------------------------------------------------------------------------------------------
1.**gold.dim_customers**
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

---------------------------------------------------------------------------------------------------------------------------------------------------------
2. **gold.dim_products**
. Purpose: Provide information about the products and their attributes

. Colunms :


| **Column Name**          | **Data Type** | **Description**                                                                                         |
| ------------------------ | ------------- | ------------------------------------------------------------------------------------------------------- |
| **product_key**          | INT           | Surrogate key uniquely identifying each product record in the product dimension table.                  |
| **product_id**           | INT           | A unique identifier assigned to the product for internal tracking and referencing.                      |
| **product_number**       | NVARCHAR(50)  | A structured alphanumeric code representing the product, commonly used for classification or inventory. |
| **product_name**         | NVARCHAR(50)  | Descriptive name of the product, including attributes such as type, color, or size.                     |
| **category_id**          | NVARCHAR(50)  | A unique identifier for the product's category, linking it to a higher-level classification.            |
| **category**             | NVARCHAR(50)  | The broader classification of the product (e.g., *Bikes*, *Components*).                                |
| **subcategory**          | NVARCHAR(50)  | A more detailed classification under the main category (e.g., product type or style).                   |
| **maintenance_required** | NVARCHAR(50)  | Indicates if the product requires maintenance (e.g., `'Yes'`, `'No'`).                                  |
| **cost**                 | INT           | The base cost of the product, represented in monetary units.                                            |
| **product_line**         | NVARCHAR(50)  | The product line or series that the item belongs to (e.g., *Road*, *Mountain*).                         |
| **start_date**           | DATE          | The date when the product became available for sale or operational use.                                 |
