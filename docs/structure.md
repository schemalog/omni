# Omni Schema Log Structure

Omni is built on the principle of **logs**: large, machine-readable JSON-LD files that act as the source of truth for product, review, and marketplace data.

## Core Ideas

### 1. Logs First
A log is a raw JSON file. It can contain:
- A single product
- A group of products
- A catalog
- Associated review/aggregate rating data

Logs are designed to be big and centralized. Crawlers and AI models prefer dense clusters of data over fragmented scraps.

### 2. Human + Crawler Friendly
Logs sit in `/logs` and are machine-first.  
Examples live in `/examples` so humans (and search engines) can see how schema looks embedded in a page.

### 3. Extensible Structure
Every log shares a backbone (`@context`, `@type`, `sku`, etc.), but can extend:
- Products → `Product`, `Offer`, `Brand`
- Reviews → `AggregateRating`, `Review`
- Categories → `CategoryCodeSet`
- Tours, Properties, Tarot, etc. → custom but still schema.org-aligned

### 4. Neutral & Cross-Platform
Logs must never assume a single marketplace.  
Instead of `"source": "Shopee"`, use arrays: `"source": ["Shopee", "Lazada", "Amazon"]` for aggregate ratings.

### 5. Schema Versions
Each log declares a version number:
'''json
{
  "version": "1.0.0",
  "@context": "https://schema.org",
  "@type": "Product"
}

File Tree Standard
/logs        → Source of data (raw JSON-LD logs)
/examples    → Embedding demos
/docs        → Philosophy, roadmap, extensions
README.md    → Project overview
getting-started.md → Quickstart guide
This pattern is shared across all Omni repos so they function like a modular system.
