Data Dictionary for Gold layer
OverView
The Gold layer is the business-level data representation , structured to support analytics and reporting use cases. it consists of dimension tables and fact tables for specific business metrics
------------------------------------------------------------------------------------------------------------------------------------------------------
1.**gold.dim_customers**
. Purpose: Store customer details enriched with demographic and geographic data

. Colunms :

| **Column Name**     | **Data Type** | **Description**                                                                       |
| ------------------- | ------------- | ------------------------------------------------------------------------------------- |
| **customer_key**    | INT           | Surrogate key uniquely identifying each customer record in the dimension table.       |
| **customer_id**     | INT           | Unique numerical identifier assigned to each customer.                                |
| **customer_number** | NVARCHAR(50)  | Alphanumeric identifier representing the customer, used for tracking and referencing. |
| **first_name**      | NVARCHAR(50)  | The customer's first name, as recorded in the system.                                 |
| **last_name**       | NVARCHAR(50)  | The customer's last name or family name.                                              |
| **country**         | NVARCHAR(50)  | The country of residence for the customer (e.g., 'Australia').                        |
| **marital_status**  | NVARCHAR(50)  | The marital status of the customer (e.g., 'Married', 'Single').                       |
| **gender**          | NVARCHAR(50)  | The gender of the customer (e.g., 'Male', 'Female', 'n/a').                           |
| **birthdate**       | DATE          | The date of birth of the customer, formatted as YYYY-MM-DD.                           |
| **create_date**     | DATE          | The date when the customer record was created in the system.                          |


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

---------------------------------------------------------------------------------------------------------------------------------------------------------
3. **gold.facts_sales**
. Purpose : Stores transactional sales data used for analytical reporting, KPIs, dashboards, and dimensional modeling.
This is the central fact table in your star schema.

. Colunms :

| **Column Name**   | **Data Type** | **Description**                                                             |
| ----------------- | ------------- | --------------------------------------------------------------------------- |
| **order_number**  | NVARCHAR(50)  | A unique alphanumeric identifier for each sales order (e.g., *SO54496*).    |
| **product_key**   | INT           | Surrogate key linking the sales record to the **gold.dim_products** table.  |
| **customer_key**  | INT           | Surrogate key linking the sales record to the **gold.dim_customers** table. |
| **order_date**    | DATE          | The date when the customer placed the order.                                |
| **shipping_date** | DATE          | The date when the order was shipped to the customer.                        |
| **due_date**      | DATE          | The date when the order payment was due.                                    |
| **sales_amount**  | INT           | Total monetary value of the order line (e.g., `price * quantity`).          |
| **quantity**      | INT           | The number of units sold in the order line.                                 |
| **price**         | INT           | The price per unit for the product in the order line.                       |

