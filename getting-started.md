Getting Started with Omni

Welcome to Omni, the schema log structure for e-commerce products and reviews. This guide shows you how to use Omni logs on your own site, whether you sell on Shopee, Lazada, Amazon, Etsy, Walmart, or your own storefront.

1. Repo Structure

Omni repos are designed to be simple and flexible:

/logs
  product-schema.json   → raw schema log files (by product or catalog)
/examples
  product-page.html     → ready-to-use HTML with JSON-LD embedded
/docs
  structure.md          → deep-dive on schema log philosophy

Logs = source of truth. Machine-friendly.

Examples = how to embed schema in a real page. Human + crawler friendly.

Docs = background, extensions, and best practices.

2. Adding Schema Logs

Each product (or group of products) should have a log file in /logs.
For example:

/logs/product-schema.json

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

3. Embedding Schema in Your Site

To make Google and other crawlers recognize your schema, embed it into your product pages as JSON-LD inside a <script> tag.

Example:

<!DOCTYPE html>
<html lang="en">
<head>
  <title>Waking Cup Dark Roast</title>
  <script type="application/ld+json">
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
  </script>
</head>
<body>
  <h1>Waking Cup Dark Roast</h1>
  <p>Our boldest coffee blend yet.</p>
</body>
</html>


Google doesn’t care what your site looks like—it cares about that <script type="application/ld+json"> block.

4. Adding Reviews

Once you have product logs, you can extend them with review or aggregate rating data.

Example:

{
  "@context": "https://schema.org",
  "@type": "AggregateRating",
  "itemReviewed": "WC123",
  "ratingValue": "4.7",
  "reviewCount": 134,
  "source": ["Shopee", "Lazada"]
}


Place this in a separate log file (e.g., /logs/reviews-schema.json) or embed directly in your product page.

5. Next Steps

Create schema logs for all your products.

Aggregate reviews from marketplaces where you sell.

Drop the JSON-LD into your site to enrich SEO with stars and ratings.

Contribute your schema logs back to this repo—or fork it to build your own.

6. Validation

Use Google’s Rich Results Test
 to confirm your schema is valid and indexable.

Omni isn’t just for coffee—it’s for every product on every platform. Start with your logs, embed them, and help build a global schema commons.
