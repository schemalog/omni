Getting Started with Omni

Welcome to Omni, the schema log structure for e-commerce products and reviews. This guide shows you how to use Omni logs on your own site, whether you sell on Shopee, Lazada, Amazon, Etsy, or any other storefront.


1. Repo Structure

Omni repos are designed to be simple and flexible:

/logs
  product-schema.json   → raw schema log files (by product and online store)
/docs
  structure.md          → notes on schema log philosophy

Logs = source of structured data sets. Machine-friendly.

Docs = background, extensions, and best practices.


2. Adding Schema Logs

Each store or group of products should have a log file in /logs.
For example, a section from a product:

wakingcup/logs/product-schema.json

   {
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
        "aggregateRating": {
            "@type": "AggregateRating",
            "ratingValue": 4.97,
            "reviewCount": 78
        },
        "reviews": [
            {
                "@type": "Review",
                "OnlineStore": "Lazada",
                "author": "Chaiyaphol P.",
                "notes": "โอ้โหแพคเกจไม่เร็วนะครับผมลองใช้แล้วถือว่าทำดีเลยแพ็คเกจของอุปกรณ์เนี่ยขอมาดีแล้วก็เท่าที่ลองใช้งานแล้วกรองได้ละเอียดมากพระเจ้ามีโอกาสจะใส่แน่นอนครับ",
                "date": "2023-03-08",
                "reviewRating": 5,
                "bestReview": 5,
                "pieces": "แพ็ก คู่",
                "image": [
                    "https://img.lazcdn.com/g/p/34d5589e2250db91701e15597b462c45.jpg_x180q80.jpg_.webp",
                    "https://img.lazcdn.com/g/ugc/b44854727ab049f9a4b49d950312a5ac_7e8ee74aa4a84794a5ed626d7fe10de9.jpg_x180q80.jpg_.webp"
                ]
            },...


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
    "sku": "WC123example",
    "name": "Waking Cup Medium Roast",
    "brand": {
      "@type": "Brand",
      "name": "Waking Cup"
    },
    "offers": {
      "@type": "Offer",
      "priceCurrency": "THB",
      "price": "250.00",
      "url": "https://shopeeexample.co.th/product/123456"
    }
  }
  </script>
</head>
<body>
  <h1>Waking Cup Medium Roast</h1>
  <p>Our best coffee blend yet.</p>
</body>
</html>


4. Next Steps

Create a schema log for all your products.

Aggregate reviews from marketplaces where you sell.

Drop the entire JSON-LD schema log into your site, and inject appropriate sections into product pages to enrich SEO. 

Use functions to calculate and display star ratings, reviews, and any other data you can use.

Contribute your schema logs back to this repo or fork it to build your own.


5. Validation

Use Google’s Rich Results Test
 to confirm your schema is valid and indexable.


Omni is for every product on every platform. Start with your logs, embed them, and help build a global schema commons.
