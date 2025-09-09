# Omni Product Schema Log

Omni is an open schema log structure for e-commerce products and reviews. It provides a unified way to represent product data and customer reviews across multiple online stores (Shopee, Lazada, Amazon, Etsy, GumRoad, etc.) in a machine-readable format.

Omni was first prototyped on Waking Cup Coffee, but the structure is designed for any product in any store worldwide.


## Why Omni?

- Product data is fragmented across platforms. Reviews live in silos. Omni provides:
- Unified product schema: define your product once, reference it across platforms.
- Cross-platform reviews: aggregate ratings from different marketplaces.
- SEO & AI benefits: embed JSON-LD schema to show rich snippets (stars, ratings) and make your data crawlable. Leaving your schema log here is like sending a probe for crawlers to discover.
- Scalability: works for small stores or giant catalogs.


## Features

📦 Product entries with SKU identifiers.
⭐ Aggregated review logs (Shopee, Lazada, Amazon, etc.).
🌐 JSON-LD ready for embedding in websites.
🔗 Extensible structure—connect products, reviews, categories, or even wholesale catalogs.

### Example
```
Product Entry
        "@type": "Product",
        "name": "กรองดริปกาแฟ คุณภาพดี แบบพับได้ กรวยดริปเปอร์ สแตนเลส ดิปกาแฟ ที่กรองกาแฟแบบสแตนเลส Dripper Stainless Steel สินค้าพร้อมส่ง",
        "sku": "4212266679",
        "brand": "89 Coffee",
        "canonical": "https://wakingcup.com/product/%e0%b8%81%e0%b8%a3%e0%b8%ad%e0%b8%87%e0%b8%94%e0%b8%a3%e0%b8%b4%e0%b8%9b%e0%b8%81%e0%b8%b2%e0%b9%81%e0%b8%9f-%e0%b8%84%e0%b8%b8%e0%b8%93%e0%b8%a0%e0%b8%b2%e0%b8%9e%e0%b8%94%e0%b8%b5-%e0%b9%81%e0%b8%9a/",
        "image": "https://wakingcup.com/wp-content/uploads/sites/3/2025/07/13coffee02.png",
        "offers": [
            {
                "@type": "Offer",
                "price": "69",
                "priceCurrency": "THB",
                "availability": "https://schema.org/InStock",
                "url": "https://wakingcup.com/product/%e0%b8%81%e0%b8%a3%e0%b8%ad%e0%b8%87%e0%b8%94%e0%b8%a3%e0%b8%b4%e0%b8%9b%e0%b8%81%e0%b8%b2%e0%b9%81%e0%b8%9f-%e0%b8%84%e0%b8%b8%e0%b8%93%e0%b8%a0%e0%b8%b2%e0%b8%9e%e0%b8%94%e0%b8%b5-%e0%b9%81%e0%b8%9a/",
                "seller": {
                    "@type": "Organization",
                    "name": "WakingCup"
                }
            },
            {
                "@type": "Offer",
                "price": "69",
                "priceCurrency": "THB",
                "availability": "https://schema.org/InStock",
                "url": "https://www.lazada.co.th/products/pdp-i4212266679.html",
                "OnlineStore": "Lazada"
            }
        ],
        "externalLinks": {
            "lazada": "https://www.lazada.co.th/products/pdp-i4212266679.html"
        },

### Review Aggregation
        "aggregateRating": {
            "@type": "AggregateRating",
            "ratingValue": 4.97,
            "reviewCount": 78,
            "source": ["Shopee", "Lazada"]
        },
}
```

## Usage

- Drop Omni JSON-LD schema sections into your product pages to enrich SEO.
- Maintain schema logs that track all your products + reviews in one place.
- Scale across platforms: centralize your catalog while letting each store keep its own sales.


## Roadmap

 - Publish reference implementation (Waking Cup).
 - Example scripts for aggregating review data.
 - Guidelines for wholesale + marketplace extensions.
 - Thai-language mirror (for Lazada/Shopee sellers in Thailand).


## Contributing

- Want to add your store’s schema logs? Fork this repo, add your data, and submit a PR. Omni is designed to grow into a global schema commons for e-commerce.


## License

MIT License. Free for anyone to use, extend, or embed.
