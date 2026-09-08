# Dr. Mona Sabaa — clinic site

Static single-page site for Dr. Mona Ibrahim Sabaa, Consultant of Dermatology &
Cosmetology, founder of Skin Care Center (Mohandessin & Sheikh Zayed, Cairo).

No build step, no dependencies. Plain HTML + CSS, one image.

```
index.html          the whole page (styles inlined in <head>)
assets/portrait.jpg lifted from the CV PDF, colour-graded in CSS
assets/og.jpg       1200x630 link-share card
assets/favicon.svg  arch mark, gold on aubergine
robots.txt
sitemap.xml
```

## Preview

```bash
cd dr-mona-site
python3 -m http.server 8080     # then open http://localhost:8080
```

Opening `index.html` directly with `file://` works too.

## Deploy

Any static host. Drop the folder in and point the domain at it:

- **Cloudflare Pages** — `npx wrangler pages deploy . --project-name dr-mona`
- **Netlify** — drag the folder onto the dashboard, or `npx netlify deploy --prod --dir .`
- **Nginx / any box** — copy the folder to the web root

## Status: PREVIEW

Live at **https://omarsaba2004.github.io/dr-mona-site/** with `noindex` set and
`robots.txt` disallowing all crawlers. This is a review link for Dr. Mona, not a
public launch.

Personal contact details from the CV have been removed pending confirmation:
the booking phone/WhatsApp number and both street addresses now show as
placeholders. `d-mona@hotmail.com` is still on the page and is still
unconfirmed — it is a personal address, not a clinic one.

## To go live

1. Add the confirmed booking number and the two branch addresses.
2. Swap `d-mona@hotmail.com` for a clinic email (2 places: the contact tile and
   the JSON-LD block).
3. Delete the `<meta name="robots" content="noindex, nofollow">` tag.
4. Set `robots.txt` back to `Allow: /` and restore the `Sitemap:` line.
5. Replace `https://omarsaba2004.github.io/dr-mona-site` with the real domain
   (canonical, og:url, og:image, JSON-LD `url` + `image`, and `sitemap.xml`).
6. Regenerate `assets/og.jpg` if the name or strapline changes.

## Notes on the content

Everything on the page is from the CV. Two spellings were corrected: *IMECS* to
**IMCAS** (consistent with the two IMCAS course entries) and *Al Kasr Al Einy* to
**Kasr Al Ainy, Cairo University**.

The "Light & Laser" section plots each device at its true wavelength on a
logarithmic 250–20,000 nm scale: Excimer/NB-UVB 308–311 nm, Q-Switched 532 nm,
Pulsed Dye 595 nm, Diode 810 nm, Nd:YAG 1064 nm, Fractional CO2 10,600 nm.

No medical claims or outcome promises are made anywhere on the page — treatments
are described by what they are, not by what they achieve.
