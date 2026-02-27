# Screaming Frog: Missing Meta Keywords — Noindex Fix

**Datum:** 2026-02-27  
**Rapport:** Missing Meta Keywords (357 URLs)

---

## Samenvatting

Van de 357 URL's die Screaming Frog flagde als "missing meta keywords":

| Categorie | Aantal | Actie |
|-----------|--------|-------|
| Kleur-pagina's (`/kleur-*`) | 28 | ✅ Noindex gezet |
| WooCommerce attribuut-archives (`pa_*`) | ~100 | ✅ Noindex gezet (78 taxonomieën) |
| `/geen-categorie/` | 1 | ✅ Noindex gezet |
| Productcategorieën, pagina's, blogposts | ~250 | ℹ️ Geen actie nodig |

## Uitgevoerde Wijzigingen

### 1. Kleur-pagina's noindex (28 pagina's)

De `/kleur-*` URL's waren WordPress pagina's (post_type=page) die kleurenrasters toonden. Geen SEO-waarde, dus via Yoast post meta (`_yoast_wpseo_meta-robots-noindex`) op noindex gezet.

**Betreft o.a.:**
- `/kleur-163-antracite/`
- `/kleur-060-purple/`
- `/kleur-044-cobalt-blue/`
- `/kleur-090-black/`
- ... en 24 andere kleur-pagina's

### 2. Alle WooCommerce attribuut-taxonomieën noindex (78 taxonomieën)

In Yoast SEO `wpseo_titles` optie alle `noindex-tax-pa_*` keys op `true` gezet. Dit betreft alle productattribuut-archives:

- `/kleur-all-weather-kussens-zi/*` (28 kleur-termen)
- `/behandeling/*` (beits, grey wash, white wash, etc.)
- `/houtsoort/*` (gebruikt/nieuw steigerhout)
- `/maat-ligbed/*`
- `/all-weather-kussens-ligbed/*`
- En alle overige attribuut-taxonomieën (afmetingen, maten, extras, etc.)

### 3. Geen-categorie noindex

De WooCommerce standaard "Geen categorie" (`/geen-categorie/`, term_id 791) via Yoast term meta op noindex gezet.

### 4. Meta Keywords — Geen actie nodig

De overige ~250 URL's (productcategorieën, pagina's en blogposts) missen een `<meta name="keywords">` tag. Dit is **bewust en correct**:

- **Google negeert meta keywords volledig sinds 2009**
- Yoast SEO heeft meta keywords standaard uitgeschakeld
- Het toevoegen van meta keywords heeft **nul SEO-waarde**
- In Screaming Frog kan dit rapport veilig genegeerd worden

## Verificatie

| Test URL | Verwacht | Resultaat |
|----------|----------|-----------|
| `/kleur-163-antracite/` | noindex | ✅ `noindex, follow` |
| `/behandeling/beits/` | noindex | ✅ `noindex, follow` |
| `/eikenhout-tafels/` | index | ✅ `index, follow` |

Reguliere productcategorieën blijven gewoon geïndexeerd.

## Technische Details

**Scripts gebruikt:**
- `noindex_attributes.sh` — Zet alle `pa_*` taxonomieën op noindex via `wp option patch update wpseo_titles`
- `noindex_kleur_pages.sh` — Zet alle kleur-pagina's op noindex via `wp eval` + `update_post_meta`
- `fix_remaining.sh` — Fix voor 2 taxonomieën waar de key niet bestond + geen-categorie noindex

**Cache:** LiteSpeed cache gepurged na alle wijzigingen.
