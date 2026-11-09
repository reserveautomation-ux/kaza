# Source snapshot (2026-11-09)

Unmodified data captured read-only from the live store https://kaza-beauty.com on 2026-11-09. Use it to verify anything in the brand bible.

| File | What it is |
|---|---|
| `products.json` | Shopify `/products.json` feed (all 12 published products) |
| `collections.json` | Shopify `/collections.json` |
| `store_meta.json` | Shopify `/meta.json` (store name, city, currency, product count) |
| `shopify_products/<handle>.json` | Shopify `/products/<handle>.js` per product (variants, prices in paise, image URLs, alt text) |
| `shopify_collections/<collection>.json` | Products in each collection |
| `store_pages/*.txt` | Visible text of homepage and policy pages |

Prices in the raw `.js` files are in paise (divide by 100 for INR).
