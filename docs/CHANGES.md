# Nymer AB, sammanfattning av ändringar

## Struktur
- Delade upp koden per ansvar: `*.html` (struktur), `style.css` (utseende), `threads.js` (bakgrundsanimation).
- `threads.js` laddas som vanligt script med dynamisk import, så animationen funkar både lokalt via `file://` och på driftsatt https.
- Ny sida `portfolio.html` med projekten, filtrerbara på kategori (Alla / Logistik / E-handel).
- Städade CSS: tog bort död kod, dubbletter och onödiga wrappers.

## Visuellt
- **Startsidan:** totalt minimal. Bara threads-animationen (WebGL), NYMER uppe till vänster, Portfölj uppe till höger, kontakt i footern.
- **Portföljsidan:**
  - Sticky header (NYMER + Portfölj) och sticky "Projekt"-block med filterflikar.
  - Projekten scrollar förbi, footern kommer först längst ner.
  - Scroll-drivna animationer: varje projekt tonar in när det scrollas fram (respekterar reducerad rörelse).
  - Symmetriska marginaler, stilrent svartvitt.
- E-postlänken i footern är kursiv och grå (inte fet, inte blå).
- Konsekvent: aldrig en-dash eller em-dash, "|" som separator i titlar.

## SEO
- **Startsidan hade noll indexerbart innehåll.** Lade till en osynlig `<h1>` (tillgänglighet + sökmotorer) utan att röra den minimala designen.
- **Structured data (JSON-LD):**
  - Startsidan: `Organization`.
  - Portföljen: `CollectionPage` + `ItemList` med alla fem projekt som `CreativeWork`.
- **Open Graph + Twitter-kort** på båda sidorna: starkare, nyckelordsrik copy (logistik, e-handel, bokningsportaler, TMS, Sundsvall) i stället för upprepad titel. Lade till `og:site_name`.
- **`og.png`** (1200x630) genererad, stilren och on-brand, för social delning.
- **`robots.txt`** + **`sitemap.xml`** tillagda för indexering.
- Innehålls-SEO:n vilar där den ska: på portföljen, där projekttexterna ger unikt, nyckelordsrikt innehåll.

## Nästa steg (ej gjort, YAGNI tills sajten växer)
- Egen sida per projekt för djupare long-tail-SEO.
- `datePublished` i schemat om aktualitet ska signaleras.
