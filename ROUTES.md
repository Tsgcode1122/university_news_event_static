# Public route inventory

This inventory was checked against the rendered `university-news-drupal` DDEV site and is represented in the current static snapshot.

| Area | Public routes |
| --- | --- |
| Homepage | `/` and `/home` |
| News | `/news` plus linked news articles, including path aliases and Drupal node fallbacks |
| Events | `/events` plus linked event pages |
| Announcements | `/announcements` plus linked announcement pages |
| Spotlights | `/spotlights` plus linked spotlight pages |
| Search | `/search/node` and `/search/node/help` are included for the public rendered search interface; Drupal server-side search is not available on Netlify |
| Taxonomy | Public `/taxonomy/term/*` pages discovered from the rendered navigation and content |
| Content pages | Public path aliases and `/node/*` fallback pages discovered from links on the seeded routes |

The current export contains 58 rendered HTML pages and 27 public assets. The configured `/archive` and `/glossary` paths returned 404 from the local Drupal site, so they were not fabricated. Drupal admin, login, account, edit/delete, private-file, and feed routes are excluded.
