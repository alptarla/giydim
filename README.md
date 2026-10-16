# Giydim website (GitHub Pages)

Static TR + EN site: landing, privacy (incl. KVKK Aydınlatma Metni), terms, support. No build step, no JS, no trackers.

## Placeholders — replace before publishing
Search for `class="ph"` or these tokens:
- `ALP_SUPPORT_EMAIL` — support/contact address (all pages)
- `ADRES` — data controller postal address (KVKK, `privacy.html`)
- `YÜRÜRLÜK_GÜNÜ` / `EFFECTIVE_DAY` — exact effective date
- `APP_STORE_URL` — App Store link once the app is live (`index.html`, `en/index.html`)
- `HUKUKÇU_KONTROLÜ` — sections to confirm with a lawyer

**Lawyer review is recommended** for privacy, terms and especially the KVKK section (cross-border transfer to RevenueCat/Apple).

## Publish at https://alptarla.github.io/giydim/
1. On github.com create a **public** repository named `giydim` under the `alptarla` account.
2. Copy the contents of this `site/` folder to the repository root (keep `.nojekyll`):
   ```sh
   cd site
   git init -b main && git add . && git commit -m "Giydim site"
   git remote add origin https://github.com/alptarla/giydim.git
   git push -u origin main
   ```
3. Repository → **Settings → Pages** → Source: *Deploy from a branch*, Branch: `main`, folder `/ (root)` → Save.
4. Wait 1–2 minutes, then open https://alptarla.github.io/giydim/, `/privacy.html`, `/terms.html`, `/support.html`, `/en/…`.
5. If you use a different URL, change `LegalLinks.base` in `Giydim/App/LegalLinks.swift` (single place).
6. In App Store Connect use: Privacy Policy URL = `…/privacy.html`, Support URL = `…/support.html`, Marketing URL = `…/` (optional). Add the Terms URL to the app description (EULA line) as well.
