# Vibe Coding for Adults

Public course home at <https://vibecodingforadults.com>.

A practical course with Almir Sarajčić for people learning to write, test and
improve their own skills, rules and workflows with coding agents. The page
presents the working curriculum, lesson format and founding beta plan.

## Start here

- `src/pages/index.astro` — the complete public page
- `src/layouts/Site.astro` — metadata, analytics, header and footer
- `src/styles/global.css` — responsive Flow + intent typography and page layout
- `src/pages/404.astro` — actual missing-page response
- `public/` — brand assets, fonts, icons, social preview and crawler files
- [LICENSE](LICENSE) — Apache 2.0 for the website source

The Flow + intent assets are distribution copies of the identity maintained at
[optimumBA/design](https://github.com/optimumBA/design/tree/main/projects/vibe/identity).
Keep their SVG paths intact. Outfit is bundled under the SIL Open Font License
in `public/fonts/OFL.txt`.

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

Review when course information, enrollment availability, brand masters or links
change. Contact: [almir@optimum.ba](mailto:almir@optimum.ba).

## Agent-readable pages

Authored Astro pages own public text; `agent-site.json` holds site identity. `npm run build` runs Astro and Python 3 `scripts/build-agent-content.py` to create page Markdown, root `.md` URLs, `llms.txt`, and sitemap entries in `dist/`. `functions/_middleware.js` serves Markdown when requested for HTML pages. Edit the sources; `dist/` is generated.
