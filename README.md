# instagram-roundabloom-carousels

Automatic posting for @roundabloom, copied from `instagram-spotseason-carousels` on 23 Nov 2026 with @roundabloom's look (cream, peach and coral, Fraunces headlines, the round bloom mark).

- Posts the next carousel in `queue/` at **8:30 am and 8:30 pm US Eastern** (each slot used once, three-hour window).
- Main timer: a cron-job.org job sends a `post-slot` event to this repository. GitHub's own schedule is a backup.
- Secret `IG_ACCESS_TOKEN`: the Meta system-user token. @roundabloom's Instagram account ID, 17841449873944440, is set in the workflow. The token is an Instagram-login token (starts with "IG", lasts 60 days, so it needs renewing); the script then uses graph.instagram.com.
- Actions > Publish carousel > Run workflow: `dry-run`, `publish-now`, or `find-account-id` (prints the Instagram accounts the token can reach).
- Drafts: write `drafts/<id>/carousel.json`, run `python3 scripts/build_slides.py <id>`, push; GitHub renders the JPEGs. Nothing is queued without the owner's approval.
