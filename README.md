Omni is an open schema log structure for e-commerce products and reviews. It provides a unified way to represent product data and customer reviews across multiple online stores (Shopee, Lazada, Amazon, Etsy, Walmart, etc.) in a machine-readable format.

Omni was first prototyped on Waking Cup Coffee, but the structure is designed for any product in any store worldwide.

Why Omni?

Product data is fragmented across platforms. Reviews live in silos. Omni provides:

Unified product schema: define your product once, reference it across platforms.

Cross-platform reviews: aggregate ratings from different marketplaces.

SEO & AI benefits: embed JSON-LD schema to show rich snippets (stars, ratings) and make your data crawlable.

Scalability: works for small stores or giant catalogs.

Features

📦 Product entries with SKU identifiers.

⭐ Aggregated review logs (Shopee, Lazada, Amazon, etc.).

🌐 JSON-LD ready for embedding in websites.

🔗 Extensible structure—connect products, reviews, categories, or even wholesale catalogs.

Example
Product Entry
{
  "@context": "https://schema.org",
  "@type": "Product",
  "sku": "WC123",
  "name": "Waking Cup Dark Roast",
  "brand": {
    "@type": "Brand",
    "name": "Waking Cup"
  },
  "offers": {
    "@type": "Offer",
    "priceCurrency": "THB",
    "price": "250.00",
    "url": "https://shopee.co.th/product/123456"
  }
}

Review Aggregation
{
  "@context": "https://schema.org",
  "@type": "AggregateRating",
  "itemReviewed": "WC123",
  "ratingValue": "4.7",
  "reviewCount": 134,
  "source": ["Shopee", "Lazada"]
}

Usage

Drop Omni JSON-LD into your product pages to enrich SEO.

Maintain schema logs that track all your products + reviews in one place.

Scale across platforms: centralize your catalog while letting each store keep its own sales.

Roadmap

 Publish reference implementation (Waking Cup).

 Example scripts for aggregating review data.

 Guidelines for wholesale + marketplace extensions.

 Thai-language mirror (for Lazada/Shopee sellers in Thailand).

Contributing

Want to add your store’s schema logs? Fork this repo, add your data, and submit a PR. Omni is designed to grow into a global schema commons for e-commerce.

License

MIT License. Free for anyone to use, extend, or embed.
