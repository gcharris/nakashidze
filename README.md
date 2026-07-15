# Nakashidze House

Static website for the **Nakashidze Family House** — 27 Ninoshvili St, Batumi, Georgia.

## Pages

| URL | File | Purpose |
|-----|------|---------|
| `/` | [`index.html`](index.html) | Home / landing page |
| `/arms` | [`arms/index.html`](arms/index.html) | **Coat of arms reference page — the target of the QR code on the commemorative plate** |
| `/tree` | [`tree/index.html`](tree/index.html) | Family tree — five generations of ancestors of Deirdre Nakashidze (Bugbee) |
| `/stories` | [`stories/index.html`](stories/index.html) | Stories & updates, incl. the family history film |

The `/arms` URL is produced by the folder `arms/` containing an `index.html`, so it resolves cleanly without a `.html` extension.

## ⚠️ The domain must be `nakashidze.com`

The QR code printed on the back of the commemorative plate points to **`nakashidze.com/arms`**.
Whatever host serves this site **must** answer at that exact domain and path, or the printed
plates will lead nowhere.

- [`CNAME`](CNAME) is set to `nakashidze.com` for **GitHub Pages** custom-domain hosting.
- You must own `nakashidze.com` and point its DNS at your host. For GitHub Pages, add the four
  `A` records (or an `ALIAS`/`ANAME` for the apex) per GitHub's custom-domain docs, then set the
  custom domain to `nakashidze.com` in the repo's **Settings → Pages**.
- If you host somewhere else (Netlify, Cloudflare Pages, etc.), delete `CNAME` and configure the
  domain there instead — but keep the apex `nakashidze.com` and the `/arms` path.

## Structure

```
.
├── index.html            # home
├── arms/
│   └── index.html        # /arms — coat of arms reference (QR target)
├── assets/
│   ├── css/style.css     # shared stylesheet
│   └── img/              # web-optimised images
├── photos/               # original source photos (WhatsApp / plate scans)
├── CNAME                 # nakashidze.com  (GitHub Pages custom domain)
└── README.md
```

## Local preview

No build step — it's plain HTML/CSS/JS. Serve the folder and open it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/ and http://localhost:8000/arms/
```

(Open via a server rather than double-clicking the file so the `/arms/` path behaves like production.)

## Image credits

- **Full heraldic achievement** (`arms-clean.jpg`) — Nadezhda Abashvili, Wikimedia Commons,
  **CC BY-SA 4.0**. Attribution is retained on the page footer; keep it if you reuse the image.
- **Historical variants** — photographed museum reference panels, after
  V. Tsikhinsky, *Caucasian Armorial* (Petrograd, 1922);
  S. Dumin & P. Grebelsky, *Noble Families of the Russian Empire*, vol. IV (Moscow, 1998);
  and the 2019 Georgian reconstruction by G. G. Mikelashvili & G. Kontridze.
- **Plate photographs** — the family's own commemorative plate.

## Next steps

- The Family, Stories, and Contact links currently point to the existing Google Site. Rebuild those
  as native pages here when ready (same pattern: a folder + `index.html` per page).
- Replace the Google Form on Contact with a native form or a `mailto:` if desired.
