# Logging System

Omni is designed to **collect and file schema logs from many contributors** into a shared commons.

## How to Submit Your Logs

1. Fork the repo.
2. Create a folder inside `/logs` named after your brand or project:
/logs/[yourbrand]
Example:
/logs/brightbeans/
brightbeans-darkroast.json
brightbeans-lightroast.json

3. Each file should:
- Be valid JSON
- Use schema.org vocab
- Include a `version` field
- Include `sku` or unique ID
- Optionally include reviews + sources

4. Submit a Pull Request. The maintainers will review, validate, and merge.

## Naming Conventions

- Files: `product-schema.json` or `brand-catalog.json`
- Use lowercase with dashes.

## Compilation

The `/logs` directory acts as a **filing cabinet**:
- Each contributor gets a subfolder.
- Big brands/catalogs may have many files.
- Small sellers may only need one.

The larger the repo grows, the more valuable it becomes to crawlers and AIs. Dense clusters of schema = better indexing + SEO benefits for all.

## Validation

Before submitting:
- Use [Google Rich Results Test](https://search.google.com/test/rich-results)
- Run `npm run validate` (tool coming soon)
- Ensure the JSON is valid and properly formatted

## Why Contribute?

- Get your products and reviews exposed to search crawlers + AI models
- Join a shared directory that acts as a **structured-data commons**
- Help grow a neutral, open infrastructure for global e-commerce
