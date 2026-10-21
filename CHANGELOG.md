# Changelog

## 1.2.2 — 2026-10-21

Stability, security and maintainability release after the full A–E audit cycle.

**Requires database schema update** (`sql/updates/mysql/1.2.2.sql`). Safe update from **1.2.1**.

### Reliability and fetch

- Shared `CacheWriter` for atomic public JSON cache writes (fetch + display-settings sync)
- Compact cache JSON (removed `JSON_PRETTY_PRINT`)
- Runtime columns: `last_status`, `last_error`, `last_cache_file`, `consecutive_failures`, `next_fetch`
- Cron/task fetch no longer rewrites full `settings_json` (prevents lost admin saves)
- Reload widget under lock; re-check published before writing public cache
- Scheduled failure backoff via `next_fetch`; manual Fetch Now ignores backoff
- Image cache reuse by URL + settings signature; max 20 new downloads per fetch
- Wall-clock time budget for scheduled (~25s) and manual (~60s) fetches
- Scheduled due-scan filters `next_fetch` / `cache_lifetime` in SQL (scan columns only)

### Frontend and embeds

- `embed.script` shares iframe private/public Cache-Control policy
- Static `site.css` / `site.js` with CSS variables (cache-safe assets in widget HTML)
- Frontend render keeps cache item order (no public-path re-sort)
- Domain registry retention cleanup on scheduled fetch only

### Security and platform

- External cron: `X-DevArt-Cron-Token` / `Authorization: Bearer` (query `?token=` fallback); invalid token → HTTP 403 without IP logging
- Feed parser: RSS 1.0/RDF, `dc:date`, enclosures, Atom published/updated, reject XML ENTITY
- Application input via `getInput()` / `$this->input`; no deprecated `curl_close` / `imagedestroy`; no `GLOB_BRACE`
- Dropped unused `#__devartrsswidgets_logs`; removed unused Options `cache_lifetime`

### Maintainability

- Central `SettingsSchema`; Support helpers; `EmbedOrchestrator`; WidgetController service split
- Admin widget edit template partials + i18n; single root installer `script.php`
- Dev-only PHPUnit for Support helpers and feed fixtures (`composer phpunit`; not packaged)

## 1.2.1 — 2026-08-25

Administrator UX alignment and language expansion.

- Packaged languages expanded to 15: en-GB, el-GR, fr-FR, de-DE, es-ES, it-IT, pt-PT, cs-CZ, nl-NL, pl-PL, ru-RU, uk-UA, ja-JP, tr-TR, zh-CN
- Hub dashboard cards (New Widget, Widgets, Settings, Modules, Domain Usage, Scheduled Tasks)
- Dashboard cache status stat cards; hub-first layout with Fetch/Cache actions
- Bordered Options groups (Fetch/Cron, Cache, Uninstall, Domain/Embeds)
- Active submenu color `#08a39a`; Import panel matches Widgets / Slider
- No database migration from 1.2.0

## 1.2.0 — 2026-08-21

Residual audit hardening (P2 + selected P3).

- Fail closed when PHP cURL is missing; removed insecure `file_get_contents` fetch fallback
- `validate.php` treats `curl` as a required PHP extension
- Removed stale lock reclaim that could break per-widget flock after 180s
- Scheduled `isDue` now uses `last_fetch` (stops retry storms on failing widgets)
- Single-widget delete requires POST CSRF token
- Cron token generator uses `random_bytes` server fallback (no `Math.random`)

## 1.1.9 — 2026-08-21

Low-risk hardening from original audits.

- Tightened stored media path and local media URL sanitization (`..`, schemes, unsafe characters)
- Module now uses Joomla `ModuleHelper::getLayoutPath` with a real `tmpl/default.php` renderer
- Automated tests remain deferred (no test harness in this repository yet)

## 1.1.8 — 2026-08-21

Packaged admin/front language packs.

- Added `el-GR`, `fr-FR`, `de-DE`, `es-ES`, `it-IT`, `pt-PT` for package, component, module and both plugins
- Machine-generated from `en-GB` via `scripts/generate-languages.py` with placeholder preservation

## 1.1.7 — 2026-08-21

Package-only update channel migration.

- `source/package/update.xml` now uses `type=package` and `element=pkg_devartrsswidgets`
- Removed the temporary component-based update descriptor
- Documentation and AGENTS rules updated to match the package-only channel

## 1.1.6 — 2026-08-21

Execution consistency for scheduled and manual fetches (Milestone D).

- Shared `FetchCoordinatorService` for external cron, Joomla task and manual Fetch Now
- `fetch_mode` fail-closed: external cron and Joomla task refuse the wrong caller
- Global flock plus per-widget locks with stale reclaim
- Bounded batch of 5 due widgets per run with truthful success/partial/failure and `WILL_RESUME` when more remain
- Unified DB/settings fetch status updates

## 1.1.5 — 2026-08-21

Security hardening for public embeds (Milestone C — Embed boundary).

- Shared `EmbedBoundaryService` for iframe and script embed domain checks
- Registry writes only after `embed_enabled` and allowed domain checks
- Hard caps (200 domains/widget, 5000 global) plus 90-day retention pruning
- Iframe uses `private, no-store` (and `allowCache(false)`) when domain policy or registry can vary the response; script embed stays `no-store`

## 1.1.3 — 2026-08-21

Admin edit performance cleanup.

- Removed unused category/article preload queries from the widget edit screen (AJAX picker already loads labels on demand)

## 1.1.2 — 2026-08-21

Security hardening for public cache data and widget lifecycle (Milestone B — Public data boundary).

- Public render DTO in webroot cache JSON (display settings only; no notes, domain policy lists, content IDs, or full feed URLs)
- Joomla Content fetch filtered by guest view levels, published categories, and language when multilanguage is enabled
- Unpublish removes public cache JSON; delete also removes image cache, uploads and domain-registry records
- `RendererService` requires a published widget before reading cache
- Unpublished widgets cannot write a new public cache file

## 1.1.1 — 2026-08-21

Security hardening for remote feed and image fetching (Milestone A — Network boundary).

- Manual HTTP redirect handling with per-hop URL validation
- Public-IP resolution and curl IP pinning to reduce SSRF / DNS-rebinding risk
- Rejection of URL userinfo credentials
- Streaming response size limit for feeds and remote images
- Pre-decode image dimension and memory budget checks before GD processing
- No automatic `CURLOPT_FOLLOWLOCATION`

## 1.1.0 — 2026-05-07

Initial repository bootstrap from DevArt Repository Template v1.0.0 with the existing DevArt RSS Widgets source tree.

- Package `pkg_devartrsswidgets` with four declared extensions
- Component `com_devart_rss_widgets` for widget management, RSS fetching, rendering, embed output, and domain usage tracking
- Site module `mod_devartrsswidget` for frontend widget output
- Content plugin `plg_content_devartrsswidgets` for `{rsswidget}` article tags
- Task plugin `plg_task_devartrsswidgets` for scheduled RSS fetch routines
- Manifest baseline set to Joomla 6.* and PHP 8.3.0
- Supported packaged language: `en-GB`

Verification status belongs in `PROJECT_STATUS.md` and must record only
confirmed Joomla testing.
