# JST AGB – GitHub Pages

Static landing page hosting the General Terms & Conditions (AGB) of JST Power Equipment GmbH.

## Files

- `index.html` — German landing page with Impressum and link to the AGB PDF
- `agb-gtc.pdf` — the AGB document (bilingual DE/EN), Stand März 2025

## Before going live

Replace the `[bitte ergänzen]` placeholders in `index.html`:

- Geschäftsführer (two names — confirm from company records)
- Telefon — main office phone for Frankfurt
- Umsatzsteuer-ID — `DE` + 9 digits
- § 18 Abs. 2 MStV — only needed if the page hosts editorial content; can be removed otherwise

Search the file for `[` to find all spots, or for the CSS class `todo`.

## Deploy to GitHub Pages

1. Create a new public repo, e.g. `jst-agb`.
2. Upload both `index.html` and `agb-gtc.pdf` to the repo root.
3. Settings → Pages → Source: `Deploy from a branch`, Branch: `main`, Folder: `/ (root)` → Save.
4. After ~1 minute, the site is live at `https://<username>.github.io/jst-agb/`.
5. The PDF is reachable at `https://<username>.github.io/jst-agb/agb-gtc.pdf`.

## Optional: custom subdomain

Settings → Pages → Custom domain: `agb.jstpower.com` (or chosen subdomain). Have DNS add a CNAME record pointing the subdomain to `<username>.github.io`. Enable "Enforce HTTPS" once DNS resolves.

## Versioning

When the AGB is updated:

1. Rename the old PDF to `agb-gtc-2025-03.pdf` (or similar) so old links keep working.
2. Upload the new PDF as `agb-gtc.pdf`.
3. Update "Stand" and "Gültig bis" in `index.html`.
4. Update "Dokument-ID" if it changed.
5. Commit. The git log preserves every version with a timestamp — useful as evidence if a customer ever disputes which AGB version applied to their contract.
