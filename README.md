# Client-Ready Project Systems — Netlify site (NOT published)

Status: local files only. Nothing has been pushed, uploaded, or published.
Repository creation, Netlify connection, and publishing all require the
user's explicit approval (approval gate).

Hosting: Netlify Free (credit-based plan, checked 2026-11-24:
300 credits/month, production deploy = 15 credits each,
Deploy Previews / branch deploys = 0 credits).

## Structure
- `_config.yml` — site settings. The canonical URL lives in `url:` only.
- `index.md` — home page
- `articles/` — articles (Markdown, Jekyll front matter)
- `Gemfile` — Jekyll 4.3 + minima theme + seo-tag / sitemap / feed plugins
- `netlify.toml` — build command `bundle exec jekyll build`, publish `_site`
- `robots.txt`, `.gitignore`

## Deploy steps (run only after approval)
1. Create the GitHub repository (name suggestion:
   `client-ready-project-systems`) and push this folder as its root.
2. In Netlify: Add new site → Import from Git → select the repository.
   Build settings are read from `netlify.toml` automatically.
3. After the first deploy, set `url:` in `_config.yml` to the production
   URL and update the Sitemap line in `robots.txt` in the same commit.
4. Create a GA4 property (free), set the Measurement ID, verify pageviews.
5. Replace affiliate link placeholders only after affiliate applications
   are approved and Japan eligibility is confirmed.

## Operating rules (credit minimization)
- Proofread on Deploy Previews (0 credits). Merge to `main` at most once
  per week — each production deploy costs 15 credits.
- No Functions, Edge Functions, or AI features (compute is billed).
- Compress images before adding them (bandwidth is 20 credits per GB).

## Tracking conventions
- SNS posts link to articles with UTM parameters, e.g.
  `?utm_source=threads&utm_medium=social&utm_campaign=clickup-vs-monday`
  (use `utm_source=x` for X posts). GA4 attributes sessions by source.
- CTA clicks are counted in each vendor's affiliate dashboard, not on-site.
- All numbers are transcribed into the tracking workbook by hand. No
  automated posting, liking, or following is used anywhere in this setup.

## Custom domain (future)
Internal links are relative paths only, and no `*.netlify.app` URL is
hard-coded in content. When a custom domain is connected: update `url:`
in `_config.yml`, update `robots.txt`, and add a 301 `[[redirects]]`
block in `netlify.toml` from the old subdomain.
