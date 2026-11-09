# Column Lineage Explorer

A synthetic, browser-based demonstration of column-level lineage across Python-style DataFrame transformations.

Click a column to highlight its upstream ancestors and downstream descendants, including their containing DataFrame cards. Blue means upstream; green means downstream; gold marks the selection. Reset or press Escape to clear. A dropdown provides an alternative to selecting columns in the diagram.

## Try it

[Open the live Explorer](https://linyuli303.github.io/ColumnLineageExplorer/)

https://github.com/user-attachments/assets/9d42f6ca-112a-42c4-bdcc-eb55b94437c9

Suggested walkthrough:
1. Select `orders_calculated.revenue`: trace quantity and unit price back to source, and revenue forward to the aggregate.
2. Select `orders_raw.quantity`: inspect its route through cleaning, enrichment, calculation, and aggregation.
3. Select `customers_raw.region`: follow region through the join and summary.
4. Enable **Include mapped control dependencies** to see declared join-key/grouping influences (dashed).

## Scope

This is **explicit, curated lineage**, not an automatic parser for arbitrary Python. All datasets, columns and rules are synthetic. Solid edges describe value dependencies. Dashed edges describe selected control dependencies. The model is not exhaustive: filter row-membership effects are not expanded into edges for every affected column. Unrelated co-inputs of a derived output are not highlighted as ancestors of the selected input itself.

## Files

- `index.html`: self-contained interactive diagram, including the embedded model.
- `lineage_model.json`: readable copy of the model for reference.
