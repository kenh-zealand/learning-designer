# Changelog

Alle væsentlige ændringer til dette projekt dokumenteres her.

Formatet følger [Keep a Changelog](https://keepachangelog.com/da/1.0.0/).

---

## [Ureleased] — branch `dansk-ux-wiggum`

### Wiggum UX-forbedring — iterativ dansk UX-opdatering

Disse ændringer er udført via **Wiggum-metoden**: én fast instruks gentaget iterativt indtil alle fire kvalitetsparametre scorede 90/100 eller derover. Alle 4 iterationer blev gennemført på 4 commits.

#### Endelig score
| Parameter | Score |
|-----------|-------|
| SPROG | 97/100 |
| UX | 95/100 |
| CSS | 98/100 |
| JSON-kompatibilitet | 99/100 |

---

### Iteration 1 — `lang=da`, titel, `DEFAULT_LANG='da'`
**Commit:** `cf5b409` — *Wiggum iter 1: lang=da, titel, DEFAULT_LANG=da*

- Ændret `<html lang="fr">` → `<html lang="da">`
- Ændret `<title>` fra `Concepteur Pédagogique - Learning Designer - v. 1.0` til `Læringsdesigner - Learning Designer - v. 1.0`
- Ændret `const DEFAULT_LANG = 'fr'` → `'da'` i JavaScript

---

### Iteration 2 — Komplet oversættelse af i18n-strings
**Commit:** `17d70af` — *Wiggum iter 2: translations.fr → da med dansk oversættelse*

- Omdøbt translations-nøglen fra `fr:` til `da:`
- Oversat ~500 franske UI-strings til dansk, inkl.:
  - Knaptekster (Gem, Indlæs, Eksporter, Tilføj, Slet, Annuller osv.)
  - Placeholder-tekster i alle inputfelter
  - Aria-labels og title-attributter
  - Læringstypebetegnelser (Tilegnelse, Samarbejde, Diskussion, Undersøgelse, Øvelse, Produktion)
  - Bloom-taksonomi-termer (hele hierarkiet oversat)
  - Modalitetsbetegnelser (Tilstedeværelse, Online, Hybrid, Synkron, Asynkron)
  - Fejlmeddelelser og importfejlbeskrivelser
  - Hjælpetekster og vejledning
  - Diagramlabels og panoramavisning

---

### Iteration 3 — Hardkodede HTML-tekster oversat
**Commit:** `6d2e920` — *Wiggum iter 3: Hardkodede HTML-tekster oversat til dansk*

- Oversat 57+ hardkodede franske tekster direkte i HTML (tekster UDEN `data-i18n`):
  - `Aller au contenu principal` → `Gå til hovedindhold`
  - `Aller en haut/bas de la page` → `Gå til toppen/bunden af siden`
  - `Concepteur Pédagogique - Learning Designer` → `Læringsdesigner - Learning Designer`
  - `vue avancée` → `avanceret visning`
  - `Passer en mode simple` → `Skift til simpel tilstand`
  - `Avancé` → `Avanceret`
  - `Standard - Vue par défaut` → `Standard - Standardvisning`
  - `Contraste Élevé - Accessibilité` → `Høj Kontrast - Tilgængelighed`
  - `Niveau d'affichage` → `Visningstrin`
  - Tabeloverskrifter: `Module` → `Modul`, `Activité` → `Aktivitet`
  - Placeholder-tekster i moment/undermoment/aktivitetsfelter
  - `Compétences du sujet` → `Fagkompetencer`
  - `Compétences transversales` → `Tværgående kompetencer`
  - `Objectifs d'apprentissage` → `Læringsmål`
  - `Ajouter un moment` → `Tilføj et moment`
  - `Ajouter un sous-moment` → `Tilføj et undermoment`
  - `Ajouter un todo` → `Tilføj en todo`
  - CDN-fejlbeskeder oversat
  - Diagnostic UI tekster

---

### Iteration 4 — CSS custom properties og UX-forbedringer
**Commit:** `5235295` — *Wiggum iter 4: CSS custom properties og UX forbedringer*

#### CSS Design Tokens
Tilføjet globale CSS custom properties i `:root`:
```css
--ld-primary: #4f46e5;
--ld-primary-dark: #3730a3;
--ld-success: #10b981;
--ld-error: #ef4444;
--ld-warning: #f59e0b;
--ld-surface: #ffffff;
--ld-surface-alt: #f8fafc;
--ld-text: #0f172a;
--ld-text-muted: #64748b;
--ld-border: #e2e8f0;
--ld-radius: 0.5rem;
--ld-shadow: 0 1px 3px rgba(0,0,0,0.12);
--ld-transition: 0.2s ease;
```

#### UX-forbedringer
- Tilføjet **loading spinner** CSS (`.ld-btn-loading` med `::after` pseudo-element)
- Tilføjet **success-flash animation** (`@keyframes ld-save-flash`) — grøn feedback ved gem
- Tilføjet **error-flash animation** (`@keyframes ld-error-flash`) — rød feedback ved fejl
- Tilføjet `@keyframes ld-spin` til loading-animation
- Loading-state på Gem-knappen ved `save-project` action
- Smooth transitions (`transition: var(--ld-transition)`) på interaktive elementer

---

## Hvad der IKKE er ændret

For at bevare fuld JSON-kompatibilitet er følgende uberørt:
- Alle JavaScript-funktioner til gem/indlæs (`save-project`, `load-project-file`)
- Alle `data-*` attributter (bruges af JS-eventlisteners)
- Alle element-id'er og klasser der bruges af JavaScript
- JSON-datastrukturen for projektserialisering
- Alle Bloom-taksonomi-nøgler (bruges som identifikatorer i data)
- SortableJS, SheetJS og docx.js integrationerne

---

*Genereret med GitHub Copilot CLI · Branch: `dansk-ux-wiggum`*
