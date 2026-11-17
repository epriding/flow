# Export implementation plan

1. Implement the export.
2. Verify compatibility.
3. Move lasting guidance to the README and remove temporary task documents when complete.

## Decision to preserve

Keep the legacy export header `customer_id`. Partner importers depend on this exact header, so renaming it to `id` would break their imports.
