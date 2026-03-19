# Application de conception pédagogique
**Auteur** : François Jourde - [https://github.com/jourde](https://github.com/jourde)

## Applications web
### ➜ [Concepteur pédagogique - learning designer](https://jourde.github.io/learning-designer/interface.html)
🔥 *Point de vigilance : bien que globalement fonctionnel, l'outil reste expérimental et peut présenter des anomalies. Je vous conseille notamment de télécharger la version que vous utilisez (fichier "main.html") afin d'assurer la compatibilité avec vos sauvegardes, en cas de mise à jour du fichier sur ce dépôt.*

### ➜ [Interface de présentation - Slide Deck](https://jourde.github.io/learning-designer/slidedeck.html)
Charger un fichier JSON produit avec le Learning Designer pour afficher le support de présentation (l'application lit le contenu des champs "présentation" des activités.

## Présentation
Le concepteur pédagogique (_learning designer_) est une application web monopage pour aider à structurer, documenter et analyser une formation, depuis les informations globales (identité, public, objectifs, compétences, outils) jusqu’au déroulé précis des activités. Elle vise à transformer une intention pédagogique en plan opérationnel lisible, tout en conservant la cohérence d’ensemble.

L’outil organise la conception en niveaux imbriqués : modules, moments, sous-moments et activités. Les activités sont l’unité centrale : elles portent la durée, le type d’apprentissage, les modalités (lieu, temps, présence formateur), l’évaluation, le contenu et les ressources, avec la possibilité d’aligner chaque activité sur des objectifs, résultats et compétences.

En complément de la saisie, l’application propose des visualisations et analyses (chronologies, répartitions, couverture d’alignement) pour repérer déséquilibres et manques. Elle intègre aussi la sauvegarde JSON, l’export multi-formats et une recherche globale pour faciliter le travail sur des conceptions longues.

N.B. : Cette application a été développée avec l'aide de chatbots d'IA générative : ChatGPT (5.2 Thinking) et Claude (Sonnet 4.5, embarqué dans Visual Studio Code).  

## Ressources
### Guides
- [**Guide d'utilisation**](https://github.com/jourde/learning-designer/wiki)
### Autres
- [**Page web associée**](https://jourde.github.io/learning-designer/)
- [**Dépôt GitHub du projet**](https://github.com/jourde/learning-designer). Vous pouvez créer des adaptations de l'application (merci de m'en tenir informé si possible).
### Infographie de la démarche
![](https://github.com/jourde/learning-designer/blob/main/images/infographie.png)

# Outils associés
- [Concepteur de personas](https://jourde.github.io/artefacts/learning-design/persona-guyane.html).
- [Interface de curseurs de formation](https://jourde.github.io/artefacts/learning-design/curseurs.html).

---

# 🇩🇰 Dansk UX-forbedring — Wiggum-metoden

Denne branch (`dansk-ux-wiggum`) indeholder en komplet dansk UX-opdatering af `interface.html`, udført via **Wiggum-metoden**: én fast instruks gentaget iterativt med en scoringsbaseret stopbetingelse.

## Hvad er ændret?

### Sprog (score: 97/100)
- Brugerfladen er oversat fra **fransk til dansk**
- `<html lang="da">` og dansk sidetitel
- ~500 UI-strings oversat i i18n-systemet
- 57+ hardkodede HTML-tekster oversat direkte

### UX (score: 95/100)
- Loading-spinner på handlingsknapper (Gem)
- Grøn success-flash ved gem
- Rød error-flash ved fejl
- Dansk inline hjælpetekst (aria-labels, title-attributter) på alle vigtige elementer

### CSS (score: 98/100)
Tilføjet CSS design tokens i `:root`:
```css
--ld-primary, --ld-success, --ld-error, --ld-warning
--ld-surface, --ld-text, --ld-border, --ld-radius
--ld-shadow, --ld-transition
```

### JSON-kompatibilitet (score: 99/100)
Al gem/indlæs-funktionalitet er bevaret uændret. Eksisterende `.json`-projektfiler kan fortsat bruges.

## Wiggum-metoden

| Parameter | Staged refinement (v1) | Wiggum (v2) |
|-----------|------------------------|-------------|
| Instruks | 5 forskellige | Én fast, gentaget |
| Stop | Fast ved iteration 5 | Dynamisk stopbetingelse |
| Output | Forudbestemt per trin | Emergent — bygger på sig selv |
| Kontrol | Manuelt per trin | Scoringsbaseret automatik |

Se `prompts/wiggum-instruks.md` for den komplette Wiggum-instruks.
