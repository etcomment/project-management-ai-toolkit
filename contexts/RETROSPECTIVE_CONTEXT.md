# Contexte de rétrospective et de post-mortem / Retrospective Context

---

## Purpose (Objectif de ce contexte)

Ce contexte structure la conduite des bilans de projet, des post-mortems post-incident et des rétrospectives de sprint. Il apporte un support méthodologique pour formaliser la grille KPT (Keep / Problem / Try), conduire l'analyse des causes racines, définir les plans d'actions préventives et capitaliser les enseignements (REX - retour d'expérience).

**L'IA ne remplace pas l'arbitrage du chef de projet.** L'IA est un outil de structuration, de catégorisation et de préparation de bases de travail. La prise de décision finale relève impérativement de la responsabilité humaine.

> [!CAUTION]
> Ne saisissez aucun nom de client, raison sociale, identifiant de connexion ou nom de personne physique dans les outils d'IA.
> N'utilisez en aucun cas l'IA pour évaluer la performance individuelle ou désigner des responsabilités personnelles.

---

## Use Case (Cas d'usage)

- Formaliser le bilan de fin de projet (revue de clôture).
- Préparer et animer la rétrospective à l'issue d'un sprint Agile/Scrum.
- Rédiger le rapport de post-mortem après une crise ou un incident majeur en production.
- Conduire l'analyse causale et bâtir un plan de prévention solide.
- Capitaliser les bonnes pratiques et les leçons apprises pour les chantiers futurs.

---

## Input (Informations à fournir à l'IA)

Après avoir chargé ce contexte, transmettez les informations ci-dessous (veillez à anonymiser rigoureusement les données confidentielles et nominatives) :

```
### Résultats et livrables du projet
(Synthèse des objectifs atteints, livrables produits et bilan global)

### Points forts et réussites (Keep)
(Pratiques efficaces, réussites collectives et facteurs clés de succès)

### Difficultés et dysfonctionnements rencontrés (Problem)
(Points de blocage, incidents, retards et écueils constatés)

### Chronologie des faits marquants
(Enchaînement chronologique des événements clés du projet, du sprint ou de l'incident)

### Retours des parties prenantes
(Perceptions et retours exprimés par le client, l'équipe de réalisation et le management)

### Axes d'amélioration souhaités (Try)
(Processus, pratiques d'ingénierie ou organisation à faire évoluer pour la suite)

### Écueils à éliminer définitivement
(Erreurs de cadrage ou défaillances à ne plus reproduire)
```

---

## Output (Livrables attendus de l'IA)

### 1. Synthèse exécutive du bilan
Résumé percutant du déroulement du projet, du sprint ou de la gestion de crise (3 à 5 lignes).

### 2. Matrice KPT (Keep / Problem / Try)

| Catégorie | Description & Analyse |
|---|---|
| Keep (À conserver) | Pratiques performantes à pérenniser |
| Problem (Dysfonctionnements) | Difficultés, frictions et faiblesses constatées |
| Try (À expérimenter) | Pistes d'amélioration concrètes à tester au prochain cycle |

### 3. Analyse causale (Causes racines)
Distinction rigoureuse entre les symptômes visibles, les causes directes et les causes profondes (processus, gouvernance, compétences).

### 4. Plan de remédiation et non-récurrence
Actions préventives concrètes et directement actionnables ciblant les causes racines identifiées.

### 5. Enseignements clés et bonnes pratiques (REX)
Capitalisation des leçons apprises et standards méthodologiques à diffuser à l'organisation.

### 6. Plan d'actions de l'équipe
Feuille de route des chantiers d'amélioration interne portés par l'équipe projet.

### 7. Éléments de transition vers les projets futurs
Directives, alertes et prérequis techniques/organisationnels à transmettre aux équipes reprenant le périmètre.

---

## Caution (Précautions d'usage)

- **Interdiction formelle de rechercher l'imputation de fautes individuelles.** La rétrospective vise l'amélioration continue des processus, des outils et du collectif.
- Ne renseignez aucun nom propre de client, société ou individu. Utilisez des dénominations par rôle (PM, Lead Dev, Représentant Client A).
- Les livrables de l'IA constituent une trame de travail : ils doivent être discutés, challengés et validés collectivement par l'équipe.
- Ne transmettez jamais de rapport de post-mortem généré par l'IA à un client sans relecture, vérification et validation par le management.
- **Les sorties de l'IA ne remplacent pas le jugement professionnel humain.**

---

## Modèle de prompt standard

Copiez ce modèle, renseignez les données du bilan et soumettez la requête :

```text
Sur la base des contextes de référence ci-dessous, structurez les éléments de notre rétrospective / post-mortem selon une perspective Chef de Projet.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de RETROSPECTIVE_CONTEXT.md]

---

## Données de la rétrospective (Données strictement anonymisées)

### Résultats et livrables du projet
(Renseigner)

### Points forts et réussites
(Renseigner)

### Difficultés et dysfonctionnements rencontrés
(Renseigner)

### Chronologie des faits marquants
(Renseigner)

### Retours des parties prenantes
(Renseigner)

### Axes d'amélioration souhaités
(Renseigner)

### Écueils à éliminer définitivement
(Renseigner)

---

## Livrables attendus

1. Synthèse exécutive du bilan (3 à 5 lignes)
2. Matrice Keep / Problem / Try
3. Analyse causale et causes racines
4. Plan de remédiation et non-récurrence
5. Enseignements clés et bonnes pratiques (REX)
6. Plan d'actions de l'équipe
7. Éléments de transition vers les projets futurs

※ Ne pas utiliser pour évaluer la performance individuelle ou rechercher des coupables.
※ Les sorties constituent une base de travail : l'équipe projet doit impérativement les valider.
```

---

## Version structurée pour Claude (Format balises XML)

Pour une utilisation avec Claude, la structure balisée suivante assure un cadrage rigoureux :

```text
<task>
Sur la base des données de rétrospective ci-dessous, formalisez la matrice Keep / Problem / Try, analysez les causes profondes, déterminez le plan de non-récurrence et formalisez le retour d'expérience (REX).
</task>
<context>
<pm_context>
[Coller ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Coller ici le contenu de RETROSPECTIVE_CONTEXT.md]
</specific_context>
</context>
<input>
【Données de la rétrospective (Données strictement anonymisées)】

### Résultats et livrables du projet
(Renseigner)

### Points forts et réussites
(Renseigner)

### Difficultés et dysfonctionnements rencontrés
(Renseigner)

### Chronologie des faits marquants
(Renseigner)

### Retours des parties prenantes
(Renseigner)

### Axes d'amélioration souhaités
(Renseigner)

### Écueils à éliminer définitivement
(Renseigner)
</input>
<constraints>
- Considérez les données fournies comme rigoureusement anonymisées (exclure tout nom propre ou élément d'identification).
- N'utilisez en aucun cas les résultats pour évaluer individuellement des collaborateurs.
- Si vous complétez des informations manquantes, mentionnez explicitement « (Hypothèse) ».
- Formulez les réponses sous forme de base de travail collaborative, à faire valider par l'équipe et son management.
</constraints>
<output_format>
1. Synthèse exécutive du bilan (3 à 5 lignes)
2. Matrice Keep / Problem / Try
3. Analyse causale et causes racines
4. Plan de remédiation et non-récurrence
5. Enseignements clés et bonnes pratiques (REX)
6. Plan d'actions de l'équipe
7. Éléments de transition vers les projets futurs
</output_format>
```
