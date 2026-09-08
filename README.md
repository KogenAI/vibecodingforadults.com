# Vibe Coding for Adults

Permanent campaign site for Kogen at <https://vibecodingforadults.com>.

The site has one job: present the “Vibe coding for adults” argument and route
readers to the canonical Kogen website and source. Product capabilities,
availability, documentation, and changing status remain owned by
<https://kogen.dev>.

## Start here

- `src/pages/index.astro` — the complete public page
- `src/layouts/Site.astro` — metadata, analytics, header and footer
- `src/styles/global.css` — responsive Kogen typography and page layout
- `src/pages/404.astro` — actual missing-page response
- `public/` — brand assets, fonts, icons, social preview and crawler files
- [LICENSE](LICENSE) — Apache 2.0, matching the Kogen repositories

## Work locally

Use Node.js 22 or newer, then run `npm ci` and `npm run dev`. Build the exact
static production output with `npm run build`; Cloudflare Pages publishes
`dist/`.

Plausible loads only on the canonical apex hostname. Local and preview builds
must not send analytics. The canonical production hostname is the apex;
`www.vibecodingforadults.com` permanently redirects to it while preserving the
path and query string.

## Publication checks

Before replacing the long-lived production deployment, verify the build,
canonical and robots metadata, sitemap, social image and favicons, security
headers, the `www` redirect, a real 404, outbound links, keyboard and narrow
layouts, Plausible delivery, and live mobile/desktop performance.

## Deployment and ownership

KogenAI owns this repository. Cloudflare account Optimum owns Pages project
`vibecodingforadults-com`, connected to `main` with `npm run build`, output
`dist`, and `NODE_VERSION=24.20.0`. A push to `main` publishes production.
Preview branch control is None: non-production branches do not deploy.
The site is unversioned: no package version, Git tags or GitHub releases.
Keep the single `Initial commit` history; amending published history requires
explicit user authorization. Issues, Projects, Wiki and pull requests are
disabled. Do not enable automated dependency PRs or security automation.
Almir owns domain renewal and the private Plausible property. The domain uses
Cloudflare DNS; retain its existing www-to-apex redirect.

Before publishing, run `npm ci` and `npm run build`, review desktop and mobile,
check all outgoing destinations, and inspect the production deployment for the
exact commit. Verify HTTPS, a real 404, metadata, assets, redirects and analytics.
If a build fails, fix the source and rebuild; never upload stale output. Roll
back through Cloudflare's prior successful deployment when available, or revert
the source and push through the same Git integration.

Change this page rarely. Review when links break, domain renewal is due,
analytics ownership changes, or a dependency/security issue affects the build.
The page explains the approach; current availability belongs to kogen.dev.
Contact: [contact@kogen.dev](mailto:contact@kogen.dev).
