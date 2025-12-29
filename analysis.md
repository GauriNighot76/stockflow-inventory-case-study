## Part 1: Code Review & Debugging

The first issue identified is the lack of SKU uniqueness validation. Since SKUs are required to be unique across the platform, allowing duplicates would cause confusion in sales tracking, supplier management, and reporting.

Another issue is that the product is directly associated with a warehouse during creation. From a business standpoint, products should exist independently, while inventory should be warehouse-specific. This design would force duplication of product records for each warehouse.

The code also commits product creation and inventory creation separately. If inventory creation fails, the product would still exist in the system, leading to inconsistent data. In production, this would be difficult to detect and fix.

Input validation is missing. The system assumes all fields are present and valid, which could result in negative prices, invalid quantities, or runtime errors.

Price handling is another concern. Monetary values should be stored using decimal precision to avoid rounding errors that can accumulate over time.

Overall, the solution should include validation, transactional integrity, separation of concerns between product and inventory, and enforcement of business rules.
