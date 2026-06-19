# DevArt RSS Widgets for Joomla

Professional RSS and Joomla Content widget platform for Joomla 6, designed for publishers, newspapers, magazines, portals, municipalities, organizations and high-traffic websites.

![Joomla](https://img.shields.io/badge/Joomla-6.x-blue)
![PHP](https://img.shields.io/badge/PHP-8.2%2B-green)
![Release](https://img.shields.io/badge/Version-1.1.0-orange)
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

- com_devart_rss_widgets
- mod_devart_rss_widget
- plg_content_devart_rss_widgets
- plg_task_devart_rss_widgets

---

## Requirements

- Joomla 6.x
- PHP 8.2+

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
- SSRF protection
- Domain access controls
- Safe output escaping
- Protected cache handling
- GDPR-oriented analytics controls
- Import validation
- Joomla native architecture

---

## Compatibility

Supported:

- Joomla 6.x
- PHP 8.2+
- Joomla native updates
- Modern Joomla MVC architecture

Not Supported:

- Joomla 3
- Joomla 4
- Joomla 5
- Legacy PHP versions

---

## Current Version

1.1.0

---

## What's New in 1.1.0

### Added

- Joomla Content Source support
- Latest Articles source mode
- Featured Articles source mode
- Categories source mode
- Selected Articles source mode
- Joomla Category Picker
- Joomla Article Picker
- Joomla Content cache generation
- Joomla Content iframe embeds
- Joomla Content JavaScript embeds

### Improved

- Content syndication capabilities
- Multi-site publishing workflows
- Administrator content selection workflow
- External widget creation workflow

### Compatibility

- Existing RSS widgets remain fully compatible
- Existing embeds continue to function
- Existing scheduler and cron workflows remain valid

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
