## Part 3: Low Stock Alerts API

The low-stock alert system operates at the company level and evaluates inventory across all warehouses owned by the company.

Alerts are generated when a product’s current stock falls below a defined threshold. These thresholds can vary by product type to reflect different business needs.

Only products with recent sales activity should trigger alerts. This avoids unnecessary notifications for inactive or discontinued products.

To make alerts actionable, the system calculates an estimated number of days until stock runs out using current inventory levels and average daily sales.

Supplier information is included in each alert so that users can immediately initiate reordering. If supplier data is unavailable, the alert should still be generated but clearly indicate the missing information.

Edge cases such as zero sales, missing suppliers, or extremely large datasets should be handled gracefully to ensure system stability and usability.
