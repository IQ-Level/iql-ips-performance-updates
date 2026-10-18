# Changelog

Both plugins are for Invision Community 4.7. Newest first.

## Performance Optimizer

| Version | Date | Changes |
| --- | --- | --- |
| 1.11.0 | 2026-10-18 | Licence key in the settings: saving activates it for the forum's domain, removing it detaches it. A background task checks it once a day, never during a page view. Without a valid licence every fix works the same; the ACP shows a message and IPS is not told about new versions. Answers of the licence server are signed (Ed25519); when it does not answer, the last known state stays. |
| 1.10.0 | 2026-10-17 | The settings page shows, for every fix, whether it works on this forum and why not (no Forums or Pages, clubs off, no Redis, datastore outside Redis, no `first_post` index, no postnotes, no PHP-FPM, templates not on disk). IPS checks for new versions on its own. |
| 1.9.0 | 2026-10-17 | Pages "Blocks" sidebar widgets are loaded with the page's other blocks: 5 fewer queries per topic page, 4 per Pages page. |
| 1.8.0 | 2026-10-16 | Pages blocks of a page in one query, with their categories one level per query. Topic page blocks: 52 → 18 ms. |
| 1.7.0 | 2026-10-15 | Template groups stored with an old theme cache key are compiled again instead of being rewritten on every request. Ends "Class … not found" errors after a cache clear. |
| 1.6.0 | 2026-10-15 | Notification emails are sent after the page has gone to the user. Application extension files are read once per request. |
| 1.5.0 | 2026-10-15 | A post author's clubs from memory and Redis. Topic pages without loading the whole forum tree. Post notes (postnotes add-on) checked once per topic. |
| 1.4.0 | 2026-10-14 | Theme tree and Pages database pages in one query. Language strings from Redis. |
| 1.3.0 | 2026-10-14 | Forum tree: one query per level instead of one per forum. |
| 1.2.0 | 2026-10-14 | The club of every club forum in one query. |
| 1.1.0 | 2026-10-14 | A topic's first and last post through the topic's own index: 4.018 → 0.001 s on a large forum. |
| 1.0.1 | 2026-10 | Language strings in REST API responses: 2.4–2.8 → 0.04–0.05 s on a large response. |
| 1.0.0 | 2026-10 | Language strings replaced in one pass, file URLs once per tag, recognize checked after the permission, datastore keys from Redis in one round trip. |

## Performance Monitor

| Version | Date | Changes |
| --- | --- | --- |
| 1.6.0 | 2026-10-18 | Free licence key (0 zł, updates without limit) in the settings: it turns on IPS's new-version notices. A background task checks it once a day, never during a page view. Measurements work the same without it. |
| 1.5.4 | 2026-10-17 | IPS checks for new versions on its own. |
| 1.5.3 | 2026-10-17 | Time of HTTP calls (Elasticsearch, external APIs). Requests of 1 s or more keep their costliest queries and HTTP calls. Pages blocks of 300 ms or more are listed with the address they were shown on. |
| 1.5.2 | 2026-10-16 | Time, calls and SQL of every Pages block. |
| 1.5.1 | 2026-10-15 | The PHP profile is a share of all requests. Cost of blocks and widgets, where PHP warnings come from, template errors grouped. |
| 1.5.0 | 2026-10-15 | PHP profile with the excimer extension: what each template spends its time on. |
| 1.4.0 | 2026-10-15 | Template and forum tree timing. |
| 1.3.1 | 2026-10-14 | Compact ACP dashboard block. |
| 1.3.0 | 2026-10-14 | 48-hour chart in the dashboard block, REST API by endpoint, query endings. |
| 1.2.0 | 2026-10 | ACP dashboard block with before and after. |
| 1.1.0 | 2026-10 | SQL queries grouped by pattern, with the code that sent them. |
| 1.0.0 | 2026-10 | Page timings, report in the ACP, JSON export. |
