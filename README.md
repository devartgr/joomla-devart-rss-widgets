# DevArt RSS Widgets for Joomla

Professional RSS and Joomla Content widget platform for Joomla 6, designed for publishers, newspapers, magazines, portals, municipalities, organizations and high-traffic websites.

![Joomla](https://img.shields.io/badge/Joomla-6.x-blue)
![PHP](https://img.shields.io/badge/PHP-8.3%2B-green)
![Release](https://img.shields.io/badge/Version-1.2.1-orange)
![License](https://img.shields.io/badge/License-GPLv3-red)

---

## Overview

DevArt RSS Widgets is a modern Joomla 6 widget platform that allows administrators to create embeddable widgets from RSS feeds or local Joomla content.

Widgets can be displayed inside Joomla websites or distributed to external websites through iframe or JavaScript embeds while using a cache-first architecture designed for production and high-traffic environments.

The package includes a Joomla component, module, content plugin and scheduled task integration.

---

## Features

### RSS Feed Widgets

Create widgets from:

- Single RSS feeds
- Multiple RSS feeds
- Aggregated RSS sources

Features:

- Feed ordering
- Per-feed item limits
- Fetch Now support
- Scheduled refresh support
- External cron support
- Static JSON cache generation

---

### Joomla Content Widgets

Create widgets directly from local Joomla content.

Supported content sources:

- Latest Articles
- Featured Articles
- Categories
- Selected Articles

Perfect for:

- News syndication
- Multi-site networks
- Municipal websites
- Sports organizations
- Editorial websites
- Content sharing partnerships

---

### Joomla Content Pickers

Includes Joomla-style selection tools:

- Category Picker
- Article Picker
- Search support
- Pagination support
- Multi-selection support
- Article ordering support

Designed for very large Joomla websites containing thousands of articles.

---

### Widget Templates

Included templates:

- Classic List
- Grid Cards
- Overlay Cards
- Compact List

All templates support:

- Theme presets
- Custom colors
- Typography controls
- Image controls
- Responsive layouts

---

### External Embeds

Widgets can be embedded on any website.

Supported methods:

#### Iframe Embed

Simple integration using an iframe.

#### JavaScript Embed

Responsive JavaScript-based integration.

Features:

- Auto Height mode
- Fixed Height mode
- Responsive resizing
- Mobile support

---

### Domain Controls

Control where widgets can be embedded.

Features:

- Global domain policy
- Allow lists
- Block lists
- Per-widget overrides
- Domain usage registry

Suitable for publishers distributing content to external websites.

---

### Analytics & GDPR

Optional analytics support for embedded widgets.

Features:

- Google Analytics 4 integration
- Built-in consent panel
- Privacy recall link
- Privacy Policy URL support
- Consent storage
- GDPR-friendly implementation

Analytics only applies to iframe and JavaScript embeds and never affects internal Joomla module rendering.

---

### Cache-First Architecture

Designed for high-performance environments.

Features:

- Static JSON cache generation
- Fetch Now processing
- Joomla Scheduled Task support
- External Cron support
- Cache status monitoring
- Cache maintenance tools

Frontend visitors never trigger feed processing.

---

### Image Processing

Features:

- Local image cache
- Resize support
- Recompression support
- WEBP generation
- Configurable retention periods

Image Modes:

- Auto
- Local
- Source

---

### Import / Export

Portable widget configuration management.

Features:

- Widget export
- Widget import
- Configuration portability
- Safe validation
- Runtime data exclusion

Cache files and generated images are never included in exports.

---

### Joomla Native Updates

Supports Joomla native updates via GitHub.

Update Server:

https://raw.githubusercontent.com/devartgr/joomla-devart-rss-widgets/main/update.xml

---

## Included Extensions

This package installs:

- `com_devart_rss_widgets`
- `mod_devartrsswidget`
- `plg_content_devartrsswidgets`
- `plg_task_devartrsswidgets`

---

## Requirements

- Joomla 6.x
- PHP 8.3.0+
- PHP cURL extension

---

## Performance

Built for production environments.

Features:

- Cache-first rendering
- Static JSON architecture
- Local image caching
- CDN friendly
- Cloudflare friendly
- Scheduler integration
- External cron integration
- Minimal frontend overhead

Suitable for:

- News portals
- Editorial websites
- Magazine websites
- Municipal websites
- Enterprise Joomla deployments
- High-volume content websites

---

## Security Highlights

- Joomla ACL support
- CSRF protection
- RSS feed validation
- SSRF protection with cURL IP pinning
- Domain access controls for embeds
- Safe output escaping
- Protected cache handling and artifact revocation
- GDPR-oriented analytics controls
- Import validation
- Joomla native architecture

---

## Compatibility

Supported:

- Joomla 6.x
- PHP 8.3.0+
- PHP cURL
- Joomla native package updates (`pkg_devartrsswidgets`)
- Modern Joomla MVC architecture

Not Supported:

- Joomla 3
- Joomla 4
- Joomla 5
- Legacy PHP versions

---

## Current Version

1.2.1

---

## Version 1.2.1

DevArt RSS Widgets **1.2.1** is the current **public** release.

### Highlights in 1.2.1

- Packaged languages expanded to 15: en-GB, el-GR, fr-FR, de-DE, es-ES, it-IT, pt-PT, cs-CZ, nl-NL, pl-PL, ru-RU, uk-UA, ja-JP, tr-TR, zh-CN
- Hub dashboard cards (New Widget, Widgets, Settings, Modules, Domain Usage, Scheduled Tasks)
- Dashboard cache status stat cards aligned with DevArt Widgets / Slider
- Bordered Options groups (Fetch/Cron, Cache, Uninstall, Domain/Embeds)
- Active administrator submenu color `#08a39a`
- Widgets list Import UI matching Widgets / Slider (`details`/`summary`)

### Compatibility

- Existing RSS and Joomla Content widgets remain fully compatible
- Existing embeds continue to function
- Existing scheduler and cron workflows remain valid
- No database migration required from 1.2.0

---

## Version 1.2.0

Previous public release.

### Highlights in 1.2.0

- Hardened remote feed and image fetching (redirects, IP pinning, cURL required)
- Hardened public embeds, domain registry caps and cache privacy headers
- Hardened public cache lifecycle and Joomla Content guest ACL filtering
- Shared fetch coordinator with fail-closed `fetch_mode` and safer scheduling
- Packaged languages: el-GR, fr-FR, de-DE, es-ES, it-IT, pt-PT
- Package-only Joomla update channel (`pkg_devartrsswidgets`)
- Joomla 6.0+ / PHP 8.3.0+ only

### Highlights since 1.1.0 (included in 1.2.0)

- Intermediate private builds 1.1.1–1.1.9 were not published separately
- Network boundary, public data boundary, embed boundary and fetch coordination security work
- Module layout wiring via Joomla `ModuleHelper`
- Media path sanitization and residual audit hardening

### Compatibility

- Existing RSS and Joomla Content widgets remain fully compatible
- Existing embeds continue to function
- Existing scheduler and cron workflows remain valid
- No database migration required from 1.1.0

### Security Highlights (expanded)

- Fail closed without PHP cURL
- SSRF hardening for remote fetches
- Image decode budgets before GD
- Embed domain policy / registry gating
- Public cache artifact revocation on unpublish/delete

---

## Author

Kostas Stathopoulos  
DevArt

https://devart.gr

GitHub Repository:

https://github.com/devartgr/joomla-devart-rss-widgets

---

## License

GNU General Public License v3.0 (GPLv3)

---

## Disclaimer / Limitation of Liability

This software is provided "as is", without warranty of any kind.

DevArt shall not be held liable for any damages, data loss, downtime, security incidents, business interruption, loss of profits, or other consequences arising from the use or inability to use this software.

Always test updates in a staging environment before deploying to production systems.
