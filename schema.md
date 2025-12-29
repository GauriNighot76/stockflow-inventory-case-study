## Part 2: Database Design

The system should separate products from warehouses to support multiple storage locations. A product represents a sellable item, while inventory represents the quantity of that product in a specific warehouse.

Companies can own multiple warehouses. Inventory acts as a linking entity between products and warehouses. This design avoids duplication and supports scalability.

To track inventory changes, an inventory history or log table is required. This enables auditing, forecasting, and analysis of stock movements.

Suppliers should be modeled as a separate entity and linked to products using a many-to-many relationship. This allows flexibility in sourcing and reordering.

Bundled products should be handled using a self-referencing relationship where a bundle contains multiple child products with defined quantities.

### Missing Requirements
Before finalizing the schema, I would ask:
- Can a product have multiple suppliers?
- How is recent sales activity defined?
- Are prices warehouse-specific or global?
- How frequently should inventory changes be logged?
- Can bundled products be sold individually?

These answers would influence indexing, constraints, and performance decisions.
