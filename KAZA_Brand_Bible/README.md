# KAZA Beauty — Product Brand Bible & Asset Library

Complete record of every product live on https://kaza-beauty.com (captured 2026-11-09): names, shades/colours, sizes, prices, descriptions, claims, and all product images, renamed and organised.

## Start here
| If you want… | Open |
|---|---|
| The full human-readable brand bible | [`KAZA_Brand_Bible.md`](KAZA_Brand_Bible.md) |
| A spreadsheet (filters, thumbnails, clickable image links) | `KAZA_Product_Catalog.xlsx` |
| One product only | `products/<category>/<ID>_<slug>/README.md` |
| Machine-readable data (AI agents / scripts) | [`data/kaza_products.json`](data/kaza_products.json) — everything in one file |
| Flat tables | `data/kaza_products.csv`, `kaza_shades_variants.csv`, `kaza_images.csv`, `kaza_brand_assets.csv`, `kaza_data_issues.csv` |
| Proof / raw source | `source_snapshot_2026-11-09/` (unmodified Shopify data) |

## Folder map
```
KAZA_Brand_Bible/
├── README.md                    ← this file
├── KAZA_Brand_Bible.md          ← full brand bible
├── KAZA_Product_Catalog.xlsx    ← same data as a workbook
├── data/                        ← JSON + CSV (all paths relative to this folder)
├── products/
│   ├── makeup/
│   │   ├── KZ-01_liquid-matte-lipstick/   Kaza Beauty Liquid Matte Lipstick
│   │   ├── KZ-02_lip-gloss/   Kaza Beauty Lip Gloss
│   │   ├── KZ-03_lip-oil/   Kaza Beauty Lip Oil
│   │   ├── KZ-04_lip-and-cheek-tint/   Kaza Beauty Lip & Cheek Tint
│   │   ├── KZ-05_blush-stick/   Kaza Beauty Blush Stick
│   │   ├── KZ-06_cushion-foundation/   Kaza Beauty Cushion Foundation
│   │   ├── KZ-07_kajal/   Kaza Beauty Kajal - Midnight Muse
│   └── skincare/
│       ├── KZ-08_glow-c-serum/   Kaza Beauty Glow C Serum
│       ├── KZ-09_clear-code-serum/   Kaza Beauty Clear Code Serum
│       ├── KZ-10_lumi-veil-cream/   Kaza Beauty Lumi Veil Cream
│       ├── KZ-11_cloud-cream/   Kaza Beauty Cloud Cream Moisturiser
│       ├── KZ-12_lip-balm/   Kaza Beauty Lip Balm
│       (each product folder = README.md + images/)
├── brand_assets/
│   ├── logos/                   ← wordmark + monogram
│   ├── website_homepage/        ← homepage banners & campaign images
│   └── creator_site_renders/    ← generic renders from the creator-site repo (not real packaging)
└── source_snapshot_2026-11-09/       ← raw captured data
```

## Product IDs
| ID | Product | Folder |
|---|---|---|
| `KZ-01` | Kaza Beauty Liquid Matte Lipstick | `products/makeup/KZ-01_liquid-matte-lipstick/` |
| `KZ-02` | Kaza Beauty Lip Gloss | `products/makeup/KZ-02_lip-gloss/` |
| `KZ-03` | Kaza Beauty Lip Oil | `products/makeup/KZ-03_lip-oil/` |
| `KZ-04` | Kaza Beauty Lip & Cheek Tint | `products/makeup/KZ-04_lip-and-cheek-tint/` |
| `KZ-05` | Kaza Beauty Blush Stick | `products/makeup/KZ-05_blush-stick/` |
| `KZ-06` | Kaza Beauty Cushion Foundation | `products/makeup/KZ-06_cushion-foundation/` |
| `KZ-07` | Kaza Beauty Kajal - Midnight Muse | `products/makeup/KZ-07_kajal/` |
| `KZ-08` | Kaza Beauty Glow C Serum | `products/skincare/KZ-08_glow-c-serum/` |
| `KZ-09` | Kaza Beauty Clear Code Serum | `products/skincare/KZ-09_clear-code-serum/` |
| `KZ-10` | Kaza Beauty Lumi Veil Cream | `products/skincare/KZ-10_lumi-veil-cream/` |
| `KZ-11` | Kaza Beauty Cloud Cream Moisturiser | `products/skincare/KZ-11_cloud-cream/` |
| `KZ-12` | Kaza Beauty Lip Balm | `products/skincare/KZ-12_lip-balm/` |

## Image naming convention
`kaza_<product-slug>_<NN>_<role>[_<shade>].<ext>`

- `NN` = position of the image in the product gallery on the live site (01 = main/hero image).
- `role` = `hero-packshot` · `shade-packshot` (one specific shade) · `shade-card` (all shades on one chart) · `infographic` · `before-after` · `model-lifestyle` · `lifestyle-packshot`.
- `shade` = clean shade name in kebab-case, when the image shows one shade.
- Example: `products/makeup/KZ-03_lip-oil/images/kaza_lip-oil_05_shade-packshot_secret-flush.jpg`.

Brand assets: `kaza_home_<NN>_<section>_<description>`, `kaza_logo_<type>_<colours>`.

## Notes for AI agents
- Join keys: `product_id` (KZ-01…KZ-12) links products ↔ shades ↔ images. `image_id` = `<product_id>-IMG<NN>`.
- Every path in JSON/CSV/XLSX is relative to this folder root.
- `shade_name` = cleaned name; `site_variant_name` = exact text on the live site (typos kept); `name_on_pack_or_shade_card` = what the brand's own artwork says.
- `net_quantity_source` tells you whether a size came from packaging artwork or is missing.
- Prices are INR, taxes included. Every product showed **Sold out** at capture time.
- Known inconsistencies on the live site are listed in `data/kaza_data_issues.csv` / section 8 of the bible.
