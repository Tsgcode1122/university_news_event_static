# Public route inventory

This inventory was checked against the rendered Drupal site during the export.

| Area | Public routes in the snapshot |
| --- | --- |
| Homepage | `/`, `/home`, and the Drupal shortlink `/node/1` |
| News | `/news`; individual news pages `/node/2` through `/node/7` |
| Events | `/events`; individual event pages `/node/8`, `/node/9`, `/node/10`, and `/node/15` |
| Announcements | Rendered on the homepage under “Announcements”; individual pages `/node/12`, `/node/13`, and `/node/14` |
| Spotlights | Rendered on the homepage under “Featured Stories”; these are featured news articles, not a separate Drupal route |
| Taxonomy pages | Public department, news-category, event-category, and announcement-type pages under `/taxonomy/term/*` discovered from public links |

The configured `/archive` and `/glossary` paths currently return 404 from the running local Drupal site, so they are not represented as fabricated pages in this export. Drupal admin, login, account, edit/delete, private-file, and feed routes are excluded.
