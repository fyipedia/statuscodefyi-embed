# statuscodefyi-embed

[![npm](https://img.shields.io/npm/v/statuscodefyi-embed)](https://www.npmjs.com/package/statuscodefyi-embed)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.7-blue)](https://www.typescriptlang.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/statuscodefyi-embed)

Embed **StatusCodeFYI** widgets — status codes, glossary terms, interactive tools, and inline elements — on any website. **8 widget types**, zero dependencies, Shadow DOM style isolation, 4 built-in themes (light, dark, sepia, auto), 2 styles (modern, clean), and live data from the [StatusCodeFYI](https://statuscodefyi.com) database.

Every widget includes a "Powered by StatusCodeFYI" backlink directing readers to the full reference.

> **Try the interactive widget builder at [widget.statuscodefyi.com](https://widget.statuscodefyi.com)**

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-statuscodefyi="entity" data-slug="codes" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/statuscodefyi-embed@1/dist/embed.min.js"></script>
```

That's it. The widget fetches data from the StatusCodeFYI API and renders with full style isolation.

## Widget Types

| Type | Usage | Description |
|------|-------|-------------|
| `entity` | `<div data-statuscodefyi="entity" data-slug="..."></div>` | Entity detail card — cable, ASN, or status code |
| `glossary` | `<div data-statuscodefyi="glossary" data-slug="..."></div>` | Glossary term definition with cross-references |
| `search` | `<div data-statuscodefyi="search" data-slug="..."></div>` | Search box linking to the full database |
| `compare` | `<div data-statuscodefyi="compare" data-slug="..."></div>` | Side-by-side entity comparison |
| `faq` | `<div data-statuscodefyi="faq" data-slug="..."></div>` | FAQ accordion with expand/collapse |
| `protocol` | `<div data-statuscodefyi="protocol" data-slug="..."></div>` | Protocol card — name, port, description, code count |
| `scenario` | `<div data-statuscodefyi="scenario" data-slug="..."></div>` | Error scenario debugging card — symptoms, diagnosis, resolution |
| `status-badge` | `<div data-statuscodefyi="status-badge" data-slug="..."></div>` | Inline 1xx/2xx/3xx/4xx/5xx colored badge |

## Widget Options

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-statuscodefyi` | entity, compare, glossary, search, faq, [tools] | required | Widget type |
| `data-slug` | e.g. "codes" | — | Entity slug from the StatusCodeFYI database |
| `data-theme` | light, dark, sepia, auto | light | Visual theme (`auto` follows OS preference) |
| `data-style-variant` | modern, clean | modern | Widget design style |
| `data-size` | default, compact, large | default | Widget size |
| `data-placeholder` | any string | "Search Status Codes..." | Search box placeholder |

## Themes

```html
<!-- Light (default) -->
<div data-statuscodefyi="entity" data-slug="codes" data-theme="light"></div>

<!-- Dark -->
<div data-statuscodefyi="entity" data-slug="codes" data-theme="dark"></div>

<!-- Sepia -->
<div data-statuscodefyi="entity" data-slug="codes" data-theme="sepia"></div>

<!-- Auto — follows OS dark/light preference -->
<div data-statuscodefyi="entity" data-slug="codes" data-theme="auto"></div>
```

## Styles

```html
<!-- Modern (default) — gradient header, rounded cards, accent colors -->
<div data-statuscodefyi="entity" data-slug="codes" data-style-variant="modern"></div>

<!-- Clean — minimal borders, data-first aesthetic -->
<div data-statuscodefyi="entity" data-slug="codes" data-style-variant="clean"></div>
```

## Web Components (Custom Elements)

```html
<statuscodefyi-entity slug="codes" theme="light"></statuscodefyi-entity>
<statuscodefyi-compare slug-a="item-a" slug-b="item-b"></statuscodefyi-compare>
<statuscodefyi-search placeholder="Search Status Codes..."></statuscodefyi-search>

<script src="https://cdn.jsdelivr.net/npm/statuscodefyi-embed@1/dist/embed.min.js"></script>
```

Use `style-variant` (not `style`) to avoid conflicts with the HTML reserved `style` attribute.

## CDN Options

### jsDelivr (recommended)

```html
<script src="https://cdn.jsdelivr.net/npm/statuscodefyi-embed@1/dist/embed.min.js"></script>
```

### Specific version

```html
<script src="https://cdn.jsdelivr.net/npm/statuscodefyi-embed@1.0.0/dist/embed.min.js"></script>
```

### npm (for bundlers)

```bash
npm install statuscodefyi-embed
```

```javascript
import 'statuscodefyi-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site
- **Zero dependencies**: No jQuery, React, or any external library
- **2 styles**: Modern (accent gradients) and Clean (minimal, data-first)
- **4 themes**: Light, Dark, Sepia, Auto (OS preference detection)
- **CORS**: StatusCodeFYI API has CORS enabled for all origins
- **MutationObserver**: Works with dynamically added elements (SPAs)
- **IntersectionObserver**: Lazy loading — widgets only fetch when entering viewport (200px margin)
- **Rich Snippets**: DefinedTerm JSON-LD injected for glossary widgets
- **Bundle size**: Tree-shaken per site — only includes tools available on StatusCodeFYI

## Learn More About Status Codes

Visit [statuscodefyi.com](https://statuscodefyi.com) — StatusCodeFYI is a comprehensive status codes reference with interactive tools, guides, and developer resources.

- **API docs**: [statuscodefyi.com/developers/](https://statuscodefyi.com/developers/)
- **Widget builder**: [widget.statuscodefyi.com](https://widget.statuscodefyi.com)
- **npm package**: [npmjs.com/package/statuscodefyi-embed](https://www.npmjs.com/package/statuscodefyi-embed)
- **GitHub**: [github.com/fyipedia/statuscodefyi-embed](https://github.com/fyipedia/statuscodefyi-embed)

## Network FYI Family

Part of [FYIPedia](https://fyipedia.com) — open-source developer tools ecosystem. Network FYI covers cables, IP networks, and protocol status codes. Hub: [wirefyi.com](https://wirefyi.com).

| Site | Domain | Focus | Package |
|------|--------|-------|---------|
| CableFYI | [cablefyi.com](https://cablefyi.com) | 151 cables, connectors, standards, compatibility | [npm](https://www.npmjs.com/package/cablefyi-embed) |
| IPFYI | [ipfyi.com](https://ipfyi.com) | ASN, ISP, IP ranges, network infrastructure | [npm](https://www.npmjs.com/package/ipfyi-embed) |
| **StatusCodeFYI** | [statuscodefyi.com](https://statuscodefyi.com) | HTTP/SMTP/gRPC status codes, protocols, debugging | **[npm](https://www.npmjs.com/package/statuscodefyi-embed)** |
| TLDFYI | [tldfyi.com](https://tldfyi.com) | TLD registry, domain extensions (coming soon) | Coming soon |

## FYIPedia Developer Tools

| Package | PyPI | npm | Description |
|---------|------|-----|-------------|
| colorfyi | [PyPI](https://pypi.org/project/colorfyi/) | [npm](https://www.npmjs.com/package/@fyipedia/colorfyi) | Color conversion, WCAG contrast, harmonies — [colorfyi.com](https://colorfyi.com) |
| emojifyi | [PyPI](https://pypi.org/project/emojifyi/) | [npm](https://www.npmjs.com/package/emojifyi) | Emoji encoding & metadata for 3,953 emojis — [emojifyi.com](https://emojifyi.com) |
| unitfyi | [PyPI](https://pypi.org/project/unitfyi/) | [npm](https://www.npmjs.com/package/unitfyi) | Unit conversion, 220 units — [unitfyi.com](https://unitfyi.com) |
| fyipedia | [PyPI](https://pypi.org/project/fyipedia/) | — | Unified CLI for all FYI tools — [fyipedia.com](https://fyipedia.com) |

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [FYIPedia](https://fyipedia.com).
