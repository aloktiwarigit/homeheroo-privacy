# HomeHeroo Legal Documents

Public hosting for HomeHeroo's user-facing legal documents (privacy policy, terms of service, deletion request form).

**Live site:** https://aloktiwarigit.github.io/homeheroo-privacy/

## What's here

| Path | URL | Purpose |
|------|-----|---------|
| `docs/legal/privacy-policy-technician.md` | `/technician/` | Privacy policy for the HomeHeroo Technician Android app (`in.homeheroo.technician`) |

## How it's published

The workflow at `.github/workflows/publish.yml` runs on every push to `main` that touches `docs/legal/**`. It uses pandoc to convert the Markdown to standalone HTML with GitHub Markdown CSS, then deploys to GitHub Pages via `actions/deploy-pages@v4`.

GitHub Pages is configured with **Source = GitHub Actions** (not legacy branch-based publishing).

## Updating a policy

1. Edit the relevant `docs/legal/*.md` file
2. Update the `**Last updated:**` date at the top
3. Commit and push to `main` — the workflow auto-publishes within ~30 seconds
4. Verify the live URL renders the new content

For breaking changes (deletion procedure changes, third-party additions), notify users via:
- In-app banner on the Settings → Privacy screen (handled by the Android apps)
- Play Console "What's new" entry on the next release

## Why a separate repo

Keeps the public legal surface decoupled from the private application code. The Android apps link to this site via the `privacy_policy_url` string resource, so changes here ship without needing an APK release.

## Contact

Data controller: Alok Tiwari · aloktiwari49@gmail.com
