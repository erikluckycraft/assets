# Je afbeeldingen permanent hosten

Acht bestanden, één keer goed neerzetten, daarna nooit meer omkijken.

---

## Waarom niet gewoon PayNow?

De velden in het dashboard staan in het theme als `image-uploader`, maar PayNow
toont ze als gewoon tekstveld — er is geen upload-knop. Je moet dus zelf ergens
hosten, en de vraag is alleen: waar blijft het staan?

Imgur viel af omdat ze sinds 30 september 2025 al het Britse verkeer blokkeren.
Discord viel af omdat hun links na een paar uur verlopen. Wat overblijft is een
plek waar **jij** de bestanden bezit.

---

## GitHub + jsDelivr — 10 minuten, gratis, permanent

GitHub gaat niet weg, jsDelivr is een gratis CDN dat wereldwijd uitlevert, en
niemand kan je bestanden opeens blokkeren. Dit is wat grote projecten gebruiken.

### Stap 1 — Repo maken

1. Ga naar [github.com/new](https://github.com/new) (gratis account als je er
   nog geen hebt)
2. Repository name: **`assets`**
3. Zet hem op **Public** — dit is belangrijk, anders kan jsDelivr er niet bij
4. Vink **Add a README file** aan
5. Klik **Create repository**

### Stap 2 — Bestanden uploaden

1. Klik in je nieuwe repo op **Add file → Upload files**
2. Sleep alle acht de PNG's uit deze map erin
3. Klik onderaan op **Commit changes**

### Stap 3 — Een release maken

Dit is de stap die het écht permanent maakt: je bevriest een versie, zodat een
latere wijziging nooit per ongeluk je live site verandert.

1. Rechts in je repo: **Releases → Create a new release**
2. Klik **Choose a tag**, typ **`v1`**, klik **Create new tag: v1**
3. Release title: `v1`
4. Klik **Publish release**

### Stap 4 — De URL's invullen

Vervang `JOUWNAAM` door je GitHub-gebruikersnaam en plak deze in het dashboard.

**Groep "Artwork":**

| Veld | URL |
|---|---|
| Hero banner | `https://cdn.jsdelivr.net/gh/JOUWNAAM/assets@v1/banner.png` |
| Logo wordmark | `https://cdn.jsdelivr.net/gh/JOUWNAAM/assets@v1/wordmark.png` |
| Turtle mascot | `https://cdn.jsdelivr.net/gh/JOUWNAAM/assets@v1/turtle.png` |
| Patron crown | `https://cdn.jsdelivr.net/gh/JOUWNAAM/assets@v1/crown.png` |

**Groep "Navigation & tiles":**

| Veld | URL |
|---|---|
| Tile 1 artwork | `https://cdn.jsdelivr.net/gh/JOUWNAAM/assets@v1/tile-1-ranks.png` |
| Tile 2 artwork | `https://cdn.jsdelivr.net/gh/JOUWNAAM/assets@v1/tile-2-coastyplus.png` |
| Tile 3 artwork | `https://cdn.jsdelivr.net/gh/JOUWNAAM/assets@v1/tile-3-bundles.png` |
| Tile 4 artwork | `https://cdn.jsdelivr.net/gh/JOUWNAAM/assets@v1/tile-4-bucks.png` |

### Stap 5 — Controleren

Plak één URL in je browser. Zie je de afbeelding, dan werkt het. De eerste keer
duurt het een paar seconden omdat jsDelivr hem nog moet ophalen; daarna is hij
overal ter wereld direct beschikbaar.

---

## Later iets vervangen

Zet het nieuwe bestand in de repo en maak een nieuwe release (`v2`). Verander
dan `@v1` in `@v2` in de acht velden. De oude versie blijft bestaan, dus je kunt
altijd terug.

Wil je die stap overslaan, gebruik dan `@main` in plaats van `@v1` — dan pakt
jsDelivr automatisch de nieuwste versie. Handig, maar je hebt dan minder
controle over wanneer je site verandert, en het kan tot 24 uur duren voor de
cache ververst.

---

## Als je liever iets anders wilt

| Waar | Kosten | Let op |
|---|---|---|
| GitHub + jsDelivr | gratis | repo moet publiek zijn |
| Cloudflare R2 | ~€0 tot een paar GB | eigen domein mogelijk, iets meer setup |
| Je eigen webhost | je hebt hem al | valt weg als je host wegvalt |
| ImgBB, Postimages | gratis | zelfde risico als Imgur: kan morgen stoppen |

De vuistregel: als je de bestanden niet zelf bezit en er niet zomaar bij kunt,
is het geen permanente oplossing.

---

## De bestanden in deze map

| Bestand | Waarvoor | Formaat |
|---|---|---|
| `banner.png` | Hero banner | 1905 × 270 |
| `wordmark.png` | CoastyMC-lettering | 1024 × 463 |
| `turtle.png` | Schildpad-mascotte | 1024 × 1024 |
| `crown.png` | Patron Wall-kroon | 1024 × 1024 |
| `tile-1-ranks.png` | Tegel 1 — Ranks | 1024 × 1024 |
| `tile-2-coastyplus.png` | Tegel 2 — Coasty+ | 1024 × 1024 |
| `tile-3-bundles.png` | Tegel 3 — Island Bundles | 1024 × 1024 |
| `tile-4-bucks.png` | Tegel 4 — Coasty Bucks | 1024 × 1024 |

Dit zijn de originelen uit je eigen designmap, alleen hernoemd zodat je in het
dashboard meteen ziet welke waar hoort. Heb je inmiddels andere plaatjes
gekozen voor een tegel, vervang dat bestand dan gewoon voor je uploadt — de
namen mogen hetzelfde blijven.
