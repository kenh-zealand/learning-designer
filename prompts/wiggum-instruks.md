# WIGGUM INSTRUKS — fast, gentages hver iteration

Du forbedrer filen `interface.html` fra learning-designer projektet.
Dit output fra denne iteration er inputtet til næste iteration.

## Din opgave (uændret ved hver iteration):

Gennemgå den aktuelle tilstand af `interface.html` og udfør
alle forbedringer du kan identificere inden for disse fire områder:

### 1. SPROG (mål: 90/100)
- Ændr `<html lang="fr">` til `<html lang="da">`
- Ændr `<title>` til `Læringsdesigner - Learning Designer - v. 1.0`
- Find ALLE franske UI-tekster (labels, placeholders, button-tekst, option-tekst, aria-labels, titles, tooltips, sektionsoverskrifter m.m.)
- Erstat alle French strings i `const translations = { fr: { ... } }` med danske oversættelser
- Erstat hardkodede franske strings i HTML (dvs. tekst UDEN `data-i18n` attribut) med dansk

### 2. UX (mål: 90/100)
- Find knapper uden loading-states og tilføj loading spinner/tekst ved async operationer
- Tilføj dansk inline hjælpetekst (title/aria-label) på knapper og inputs der mangler det
- Tilføj visuelt success/error feedback (f.eks. grøn/rød flash på save-knapper)
- Identificér flows der kræver mere end 3 klik og simplificér

### 3. CSS (mål: 90/100)
- Tilføj CSS custom properties i `:root` blokken:
  ```css
  :root {
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
  }
  ```
- Erstat hardkodede farver med CSS custom properties der hvor det giver mening
- Tilføj `transition: var(--ld-transition)` på interaktive elementer
- Forbedr læsbarhed (line-height: 1.5, font-size på labels)

### 4. JSON-KOMPATIBILITET (mål: 90/100)
- Rør IKKE ved JavaScript-funktioner der håndterer gem/indlæs
- Bevar alle `data-*` attributter
- Bevar alle id'er og klasser der bruges af JS
- Bevar al eksisterende funktionalitet

## Stopbetingelse — evaluer efter hver iteration:

Giv en score fra 0-100 på hver parameter:

  [ ] SPROG:  Ingen franske tekster tilbage               /100
  [ ] UX:     Alle primære flows under 3 klik             /100
  [ ] CSS:    Custom properties implementeret              /100
  [ ] JSON:   Gem/indlæs kompatibelt med originalen       /100

STOP og rapportér "WIGGUM KOMPLET" når:
  → Alle fire parametre scorer 90 eller derover
  → ELLER 5 iterationer er gennemført

Ellers: angiv hvilke parametre der mangler og fortsæt.

---

## Nøgleoplysninger om filstrukturen

- `const translations = { fr: { ... } }` ved ca. linje 9430 — her er ALLE i18n strings
- `const DEFAULT_LANG = 'fr'` ved ca. linje 7212
- HTML-elementer bruger `data-i18n="key"` til oversættelse
- Hardkodede franske tekster uden `data-i18n` attribut skal oversættes direkte i HTML
- CSS `:root` blok er ved ca. linje 254-264

## Dansk oversættelsesvejledning (vigtige termer)

| Fransk | Dansk |
|--------|-------|
| Formation | Uddannelse/Kursus |
| Module | Modul |
| Activité | Aktivitet |
| Moment | Moment/Del |
| Sous-moment | Undermoment |
| Objectifs | Læringsmål |
| Compétences | Kompetencer |
| Résultats d'apprentissage | Læringsresultater |
| Formateur | Underviser |
| Concepteur | Designer |
| Enregistrer | Gem |
| Charger | Indlæs |
| Exporter | Eksporter |
| Importer | Importer |
| Nouveau/Nouvelle | Ny/Nyt |
| Ajouter | Tilføj |
| Supprimer | Slet |
| Annuler | Annuller |
| Fermer | Luk |
| Confirmer | Bekræft |
| Créer | Opret |
| Modifier | Rediger |
| Dupliquer | Dupliker |
| Précédent | Forrige |
| Suivant | Næste |
| Tout afficher | Vis alt |
| Tout replier | Fold alle sammen |
| Tout déplier | Fold alle ud |
| Rechercher | Søg |
| Filtrer | Filtrer |
| Thème | Emne |
| Description | Beskrivelse |
| Présentation | Præsentation |
| Évaluation | Evaluering |
| Notes | Noter |
| Ressources | Ressourcer |
| Outils | Værktøjer |
| Paramètres | Parametre |
| Vue | Visning |
| Afficher | Vis |
| Masquer | Skjul |
| Standard | Standard |
| Avancé | Avanceret |
| Distanciel | Online (fjernundervisning) |
| Présentiel | Tilstedeværelse (fysisk) |
| Hybride | Hybrid |
| Synchrone | Synkron |
| Asynchrone | Asynkron |
| Présent | Til stede |
| Absent | Fraværende |
| Tolérance | Tolerance |
| Durée | Varighed |
| Regroupement | Gruppering |
| Groupe entier | Hel klasse |
| Individuel | Individuel |
| Sous-groupe | Undergruppe |
