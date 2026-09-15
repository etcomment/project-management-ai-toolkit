# Contexte de revue transversale PMO / PMO Review Context

---

## Purpose (Objectif de ce contexte)

Ce contexte permet au PMO et au management d'effectuer une revue transversale multi-projets, afin d'identifier les projets en situation critique, les risques partagés, les chefs de projet (PM) ou chantiers nécessitant un soutien, et les candidats à l'escalade managériale.

**L'IA ne remplace pas l'arbitrage du chef de projet ni de la direction.** L'IA est un outil de structuration, de catégorisation et de préparation de bases de travail. La décision finale doit impérativement être prise par un responsable humain.

> [!CAUTION]
> N'utilisez jamais les livrables de l'IA pour l'évaluation individuelle ou des décisions RH.
> Ne saisissez aucun nom de client, raison sociale, nom de collaborateur, clause contractuelle ou identifiant/clé d'accès.
> N'introduisez aucune appréciation personnelle ou évaluation individuelle relative aux chefs de projet.

---

## Use Case (Cas d'usage)

- Examiner transversalement la situation d'un portefeuille de projets.
- Identifier et prioriser les projets en situation critique (alerte rouge/orange).
- Détecter les causes racines ou difficultés récurrentes communes à plusieurs projets.
- Cartographier les projets et PM nécessitant un renfort ou un accompagnement d'urgence.
- Élaborer la trame d'un reporting PMO destiné au comité de direction (Comex/Codir).

---

## Input (Informations à fournir à l'IA)

Après avoir chargé ce contexte, transmettez les informations ci-dessous (veillez à anonymiser rigoureusement les données confidentielles et personnelles) :

```
### Liste des projets (utiliser des identifiants abstraits : « Projet A », « Projet B »)

| ID Projet | État d'avancement | Nb Incidents (Issues) | Risques majeurs | Rôle PM référent | Contexte Client | Situation Équipe / Staffing | Prochain jalon / Échéance | Besoin d'appui PMO |
|---|---|---|---|---|---|---|---|---|
| Projet A | | | | | | | | |
| Projet B | | | | | | | | |
| Projet C | | | | | | | | |

### Signaux faibles et alertes transversales
(Lister les tendances récurrentes ou alertes observées sur plusieurs chantiers)

### Projets sous tension nécessitant un renfort
(Identifier les projets nécessitant une intervention PMO et en expliciter les motifs)

### Contraintes d'organisation et de compétences
(Difficultés structurelles : staffing, compétences rares, charge/capacité)
```

---

## Output (Livrables attendus de l'IA)

### 1. Registre des projets critiques
Liste des projets nécessitant une vigilance renforcée immédiate et justification factuelle du niveau de criticité.

### 2. Facteurs de risque transversaux et récurrences
Synthèse des dysfonctionnements, points de blocage et tendances communes observés à l'échelle du portefeuille.

### 3. Cartographie des besoins d'accompagnement (PM & Projets)
Identification ciblée des projets et des profils/rôles nécessitant un soutien opérationnel du PMO ou de la direction.

### 4. Arbitrages et dossiers d'escalade
Liste des blocages et risques critiques justifiant une saisine de la direction générale ou des comités de pilotage.

### 5. Plans d'amélioration transversaux
Recommandations d'actions structurelles à mener sur les processus, la gouvernance ou le staffing.

### 6. Synthèse exécutive pour la Direction (Executive Summary)
Trame d'un flash report synthétique calibré pour une restitution de 1 à 2 minutes aux décideurs.

### 7. Plan de contrôle et prochaines actions PMO
Checklist des vérifications et démarches immédiates incombant au PMO.

---

## Caution (Précautions d'usage)

- **Interdiction formelle d'exploiter les sorties pour l'évaluation RH ou individuelle.** La revue PMO se focalise exclusivement sur l'optimisation des processus, des équipes et la sécurisation des livrables projets.
- Ne mentionnez aucun nom de client, société ou individu. Utilisez des dénominations génériques (« Projet A », « PM Référent »).
- N'introduisez aucune information d'ordre personnel ou disciplinaire.
- Ne transmettez aucune donnée contractuelle, tarifaire ou identifiant technique.
- **Les sorties de l'IA ne valent pas décision managériale.** L'arbitrage final relève de l'autorité humaine.

---

## Modèle de prompt standard

Copiez ce gabarit, complétez les données projets et soumettez la requête :

```text
Sur la base des contextes ci-dessous, réalisez une revue transversale PMO de notre portefeuille de projets.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de PMO_REVIEW_CONTEXT.md]

---

## Portefeuille de projets (Données anonymisées - noms de projets abstraits)

| ID Projet | État d'avancement | Nb Incidents (Issues) | Risques majeurs | Rôle PM référent | Contexte Client | Situation Équipe / Staffing | Prochain jalon | Besoin d'appui PMO |
|---|---|---|---|---|---|---|---|---|
| Projet A | | | | | | | | |
| Projet B | | | | | | | | |
| Projet C | | | | | | | | |

### Signaux faibles et alertes transversales
(Renseigner)

### Projets sous tension nécessitant un renfort
(Renseigner)

### Contraintes d'organisation et de compétences
(Renseigner)

---

## Livrables attendus

1. Registre des projets critiques et justifications
2. Facteurs de risque transversaux et récurrences
3. Cartographie des besoins d'accompagnement (PM & Projets)
4. Arbitrages et dossiers d'escalade
5. Plans d'amélioration transversaux
6. Synthèse exécutive pour la Direction
7. Plan de contrôle et prochaines actions PMO

※ Ne pas utiliser les sorties de l'IA pour l'évaluation individuelle ou RH.
※ Les sorties constituent une base de travail d'aide à la décision : l'arbitrage final revient exclusivement aux responsables humains.
```

---

## Version structurée pour Claude (Format balises XML)

Pour une utilisation avec Claude, la structure XML ci-dessous garantit une stricte séparation entre le mandat, les contextes, les données et les contraintes :

```text
<task>
Réalisez une revue transversale PMO du portefeuille de projets ci-dessous.
Identifiez les projets critiques, les risques transversaux, les besoins d'appui opérationnel et les arbitrages nécessitant une escalade.
</task>
<context>
<pm_context>
[Coller ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Coller ici le contenu de PMO_REVIEW_CONTEXT.md]
</specific_context>
</context>
<input>
【Portefeuille de projets (Données anonymisées - noms de projets abstraits)】

| ID Projet | État d'avancement | Nb Incidents (Issues) | Risques majeurs | Rôle PM référent | Contexte Client | Situation Équipe / Staffing | Prochain jalon | Besoin d'appui PMO |
|---|---|---|---|---|---|---|---|---|
| Projet A | | | | | | | | |
| Projet B | | | | | | | | |

### Signaux faibles et alertes transversales
(Renseigner)

### Projets sous tension nécessitant un renfort
(Renseigner)

### Contraintes d'organisation et de compétences
(Renseigner)
</input>
<constraints>
- Traitez l'ensemble des données comme strictement anonymisées (aucun nom propre de client, personne ou donnée contractuelle).
- N'utilisez en aucun cas les résultats pour de l'évaluation individuelle ou RH.
- Si vous complétez des informations manquantes, mentionnez explicitement « (Hypothèse) ».
- Formulez les réponses sous forme d'aide à la décision, l'arbitrage final revenant au responsable humain.
</constraints>
<output_format>
1. Registre des projets critiques et justifications
2. Facteurs de risque transversaux et récurrences
3. Cartographie des besoins d'accompagnement (PM & Projets)
4. Arbitrages et dossiers d'escalade
5. Plans d'amélioration transversaux
6. Synthèse exécutive pour la Direction
7. Plan de contrôle et prochaines actions PMO
</output_format>
```
