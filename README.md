# labelrelay.nl

The public website of LabelRelay: plain HTML and CSS, no build step, no cookies, no third-party
requests. Dutch at `/`, English at `/en/`.

This repository is public. Never commit keys, tokens, customer data, internal URLs or anything
from the app repository that is not meant for merchants.

## Preview

Open `index.html` in a browser.

## Keep in step

- Prices and plan texts match the app. Change them in the app first, then here.
- The footers carry the business details Dutch law asks for (name, address, KvK, VAT, email).
- The privacy pages name GitHub Pages and TransIP Email. If either changes, update both pages.

Assets: `assets/icon.svg` is LabelRelay's own icon (an original drawing); the site uses system
fonts only, so no font licences apply.

## Going live on GitHub Pages

1. On GitHub: Settings, Pages, source "Deploy from a branch", branch `main`, folder `/`.
2. On GitHub: profile Settings, Pages, "Add a domain", `labelrelay.nl`; add the TXT record it shows
   at TransIP and verify.
3. At TransIP, DNS of `labelrelay.nl`: remove the default A record(s) for `@` and `www`, then add
   the records from GitHub's "Managing a custom domain for your GitHub Pages site" page (check them
   there when you do this):
   - `@` A `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `@` AAAA `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
   - `www` CNAME `koodimi.github.io.`
   - Touch only these site records and the GitHub verification TXT record of step 2. Leave every
     mail record alone (MX, SPF, DKIM, DMARC and anything for `notify`).
4. Back in Settings, Pages: once the certificate is ready, tick "Enforce HTTPS".
