# stillpointinducer.com

Product microsite for the **Still Point Inducer™** by [The Upledger Institute International, Inc.](https://www.upledger.com/)

## About

A static single-page site hosted on GitHub Pages. It markets the Still Point Inducer™ — a physical wellness device inspired by Dr. John E. Upledger's CranioSacral Therapy — and directs visitors to the external shop to purchase.

## File Structure

```
stillpointinducer.com/
├── index.html          # Single-page site (all content)
├── styles.css          # Custom CSS (grid layout, CSS variables, responsive)
├── robots.txt          # Crawler directives
├── CNAME               # GitHub Pages custom domain (stillpointinducer.com)
├── favicon.ico
├── apple-touch-icon.png
└── img/
    └── logo-uii.png    # Upledger Institute International logo
```

## Schema.org Structured Data

Structured data is implemented as a single JSON-LD `@graph` block in `<head>`. It covers four types:

| Type | @id anchor | Purpose |
|---|---|---|
| `Organization` | `#organization` | The Upledger Institute International, Inc. |
| `WebSite` | `#website` | Site identity and publisher reference |
| `Product` | `#product` | Still Point Inducer™ with `Offer` — enables Google Product rich results |
| `VideoObject` | `#video` | SproutVideo product overview embed |

### Pending: VideoObject thumbnailUrl

The `thumbnailUrl` field in the `VideoObject` node is a **required property for Google Video rich results** and is currently set to a placeholder. To complete the VideoObject:

1. Log into the [SproutVideo dashboard](https://app.sproutvideo.com/)
2. Locate video `ac90d6b31918eecc25`
3. Copy the publicly accessible thumbnail image URL
4. Replace the placeholder string in `index.html` at the `"thumbnailUrl"` line

Until this is done, the `Organization`, `WebSite`, and `Product` nodes validate cleanly. Only the `VideoObject` will show a warning in the Rich Results Test.

## Analytics & Tracking

Google Tag Manager container **GTM-KX8GHZH** is loaded in `<head>` and via noscript fallback in `<body>`.

## External Dependencies

| Service | Purpose | URL |
|---|---|---|
| shop.iahe.com | Purchase destination | https://shop.iahe.com/Still-Point-Inducer |
| upledger.com | Parent organization site | https://www.upledger.com/ |
| iahp.com | Related practitioner directory | https://www.iahp.com/ |
| SproutVideo | Product video hosting | https://videos.sproutvideo.com/ |
| NetSuite | Product image CDN | https://698760.app.netsuite.com/ |
| Google Tag Manager | Analytics orchestration | GTM-KX8GHZH |

## Validation

After any changes to the structured data, verify with:

- **Google Rich Results Test** — https://search.google.com/test/rich-results
- **Schema.org Validator** — https://validator.schema.org/
- **Google Search Console** — Enhancements → Products (after indexing)

## Development

No build step required. Edit `index.html` and `styles.css` directly. Changes deployed by pushing to `main`; GitHub Pages serves the result at https://stillpointinducer.com/.

## Copyright

© The Upledger Institute International, Inc.®
