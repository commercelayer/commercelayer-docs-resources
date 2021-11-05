---
description: The price object and its fields
---

# Prices

SKUs can have a price for each price list. When you create a line item, it gets the price associated with the order's price list.

Price values (`amount_cents` and `compare_at_amount_cents`) must be expressed **in cents** with the only exception of `HUF` and `JPY` currencies which do not have decimals (e.g. 100$ → `"amount_cents": 10000`, 100Ft → `"amount_cents": 100`, 100¥ → `"amount_cents": 100`).
