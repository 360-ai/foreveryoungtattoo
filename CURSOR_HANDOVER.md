# Forever Young Tattoo Atelier — Cursor Handover

## Projektstruktur (so muss der Ordner aussehen)

```
forever-young/
├── index.html                  ← Hauptdatei (forever-young-tattoo.html umbenennen)
├── impressum.html              ← noch zu erstellen
├── datenschutz.html            ← noch zu erstellen
├── agb.html                    ← noch zu erstellen
│
├── images/
│   ├── logo-forever-young.png  ✅ bereit (Hero-Logo, freigestellt)
│   ├── logo-tabea.png          ✅ bereit (Nav-Logo oben links, freigestellt)
│   ├── desert.png              ✅ bereit (Hero-Hintergrund Wüstenstraße)
│   ├── tabea.jpg               ❌ fehlt — Foto von Tabea für "Über mich" Section
│   ├── tattoo-1.jpg            ❌ fehlt — Portfolio Bild 1 (breites Format 2:1)
│   ├── tattoo-2.jpg            ❌ fehlt — Portfolio Bild 2 (quadratisch)
│   ├── tattoo-3.jpg            ❌ fehlt — Portfolio Bild 3 (hochformat, tall)
│   ├── tattoo-4.jpg            ❌ fehlt — Portfolio Bild 4
│   ├── tattoo-5.jpg            ❌ fehlt — Portfolio Bild 5
│   ├── tattoo-6.jpg            ❌ fehlt — Portfolio Bild 6 (breites Format 2:1)
│   ├── tattoo-7.jpg            ❌ fehlt — Portfolio Bild 7
│   ├── tattoo-8.jpg            ❌ fehlt — Portfolio Bild 8
│   └── tattoo-9.jpg            ❌ fehlt — Portfolio Bild 9
│
└── fonts/
    ├── Lobster-Regular.ttf     ❌ herunterladen (fonts.google.com/specimen/Lobster)
    ├── LilitaOne-Regular.ttf   ❌ herunterladen (fonts.google.com/specimen/Lilita+One)
    ├── Montserrat-Light.ttf    ❌ herunterladen (fonts.google.com/specimen/Montserrat)
    ├── Montserrat-Regular.ttf  ❌
    ├── Montserrat-Medium.ttf   ❌
    └── Montserrat-SemiBold.ttf ❌
```

---

## Design System

### Farben (CSS Variablen)
```css
--bg:       #1a1008   /* Haupt-Hintergrund: dunkles Tabak-Braun */
--bg2:      #221508   /* Sections: etwas heller */
--bg3:      #2c1c0a   /* Cards */
--panel:    #120b04   /* Footer / Nav */
--sun:      #FFC200   /* Primär: helles Amber-Gelb (Schild-Farbe) */
--outline:  #6b1500   /* Dunkelrot-Braun: Schrift-Kontur */
--outline2: #8b2000   /* Etwas heller für Borders */
--rust:     #c43d0a   /* Akzent Orange-Rot */
--cream:    #f5e8c8   /* Heller Fließtext */
--tan:      #c8a870   /* Warm-beige Fließtext */
--muted:    #7a6040   /* Gedämpfte Labels */
```

### Schriften
```css
--f-script: 'Lobster', cursive        /* Script: Forever / Tabea / Headlines */
--f-round:  'Lilita One', cursive     /* Cooper-Black-vibe: Young / Leistungen */
--f-sans:   'Montserrat', sans-serif  /* Body / Labels / Nav-Links */
```

**Wichtig:** Fonts sind aktuell als lokale @font-face eingebunden (fonts/ Ordner).
Falls die Seite online deployed wird (Netlify/Cloudflare), kann man auf Google Fonts CDN
umstellen — dann `<link href="https://fonts.googleapis.com/css2?family=Lobster&family=Lilita+One&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">` wieder aktivieren.

### Ästhetik / Stil
- **70s Americana / Vintage Road Trip** — Monument Valley, Easy Rider, Vinyl-Cover
- **Grain-Overlay** auf body::before — dezentes Film-Korn (opacity .04)
- **Sunburst** im CTA-Bereich via repeating-conic-gradient
- Alle Schriften mit `-webkit-text-stroke: 1.5px var(--outline)` — sauberer einfacher Outline

---

## Bilder die eingebunden sind (bereits freigestellt)

### logo-forever-young.png
- Hero-Section, zentriert
- Klasse: `.hero-logo-img` — width: min(620px, 88vw)
- Weißer Hintergrund wurde per Python/Pillow entfernt
- Gold/Orange Logo auf transparentem Hintergrund

### logo-tabea.png
- Navigation oben links
- Zeigt: "Tabea Scholz / Tätowierungen" (ohne Telefonnummer)
- Höhe: 46px in der Nav

### desert.png
- Hero-Hintergrund (Monument Valley Wüstenstraße von Instagram)
- CSS-Filter: `brightness(.45) saturate(.75) sepia(.3)` für dezenten Look
- Darüber liegt ein radial-gradient als Overlay

---

## Placeholder-Variablen (noch zu ersetzen)

Suchen & Ersetzen in Cursor:

| Placeholder     | Ersetzen mit                    |
|----------------|---------------------------------|
| `{{ort}}`      | z.B. "Bochum" oder "Dortmund"   |
| `{{whatsapp}}` | Nummer ohne +, z.B. 4915120427995 |
| `{{telefon}}`  | z.B. 0151 2042 7995             |
| `{{adresse}}`  | Straße, PLZ Ort                 |
| `{{jahr}}`     | 2025                            |

---

## Seitenstruktur / Sections

1. **NAV** (fixed) — Logo-Bild links, Nav-Links rechts, WhatsApp-CTA-Button
2. **HERO** — Vollbild Wüsten-BG, Forever Young Logo-PNG, Tagline, 2 Buttons
3. **STRIP** — Scrollender Ticker: Stile & "Termine nach Vereinbarung"
4. **PORTFOLIO** — 3-spaltig, 9 Bilder (wide/tall Varianten), Klick → Lightbox
5. **LIGHTBOX** — Vollbild, Pfeil-Navigation, Keyboard (← → Escape)
6. **STILE & TECHNIKEN** — 6 Cards: Fine Line, Blackwork, Old School, Neo Traditional, Lettering, Cover-Up
7. **ÜBER MICH** — 2-spaltig: Bild (tabea.jpg) + Text + Signatur
8. **KONTAKT** — 3 Cards: WhatsApp, Instagram, Adresse + Booking-Hinweis
9. **CTA BAND** — Sunburst-BG, Script-Headline, WhatsApp-Button
10. **FOOTER** — Logo, Copyright, Impressum/Datenschutz/AGB Links

---

## Bekannte TODOs / Offene Punkte

- [ ] `tabea.jpg` besorgen (Foto von Tabea für Über-mich)
- [ ] 9 Portfolio-Bilder von Tabea besorgen (tattoo-1.jpg bis tattoo-9.jpg)
- [ ] Fonts herunterladen und in `fonts/` ablegen
- [ ] Alle `{{placeholder}}` mit echten Daten füllen
- [ ] Impressum erstellen (Pflicht in DE!)
- [ ] Datenschutz erstellen (DSGVO!)
- [ ] AGB erstellen (optional aber empfohlen)
- [ ] WhatsApp-Link testen (wa.me/{{whatsapp}})
- [ ] Instagram-Link prüfen (@foreveryoung.tattoo)
- [ ] Mobile Nav: Hamburger-Menü noch nicht implementiert (Nav-Links verschwinden auf Mobile)
- [ ] Optional: Kontaktformular statt nur WhatsApp
- [ ] Deployment auf Cloudflare Pages oder Netlify

---

## Deployment (Cloudflare Pages — empfohlen für 360ai)

```
1. Ordner `forever-young/` auf GitHub pushen
2. Cloudflare Pages → "Connect to Git" → Repository wählen
3. Build settings: kein Build-Command, Output: /  (statisch)
4. Domain: z.B. foreveryoung-tattoo.de über Cloudflare DNS
```

Oder Netlify Drag & Drop:
```
1. netlify.com → "Deploy without connecting to Git"
2. Ganzen Ordner reinziehen → fertig
3. Custom Domain dann über Cloudflare DNS einstellen
```

---

## Wichtige Cursor-Prompts zum Weitermachen

**Mobile Nav Hamburger:**
> "Add a hamburger menu for mobile (max-width 900px). Use pure CSS checkbox hack or minimal JS. Style it with the existing color variables --sun and --outline2."

**Impressum erstellen:**
> "Create impressum.html for a German Kleingewerbe called 'Forever Young Tattoo Atelier', owner Tabea Scholz, [Adresse]. Match the dark 70s design of index.html."

**Mehr Portfolio-Bilder:**
> "The gallery currently has 9 items with data-index attributes. Add 3 more items to #galleryGrid following the same pattern. Keep the wide/tall layout logic."

**Formular statt nur WhatsApp:**
> "Add a simple contact form section before #kontakt. Fields: Name, Idee/Motiv (textarea), Wunschgröße. Style matching existing dark bg3 cards. Use Netlify Forms (add netlify attribute to form tag)."
