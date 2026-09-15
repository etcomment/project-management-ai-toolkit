# Contexte de gestion des incidents qualité / Quality Issue Context

---

## Purpose (Objectif de ce contexte)

Ce contexte structure l'analyse des anomalies critiques, défauts passés à travers les mailles de relecture, insuffisances de couverture de test et non-conformités qualité. Il apporte un support méthodologique pour caractériser l'incident, conduire l'analyse causale (causes directes et facteurs contributifs), définir le plan d'actions correctives et préventives (CAPA) et préparer la trame de communication.

**L'IA ne remplace pas l'arbitrage du chef de projet.** L'IA est un outil d'aide à la structuration, à l'analyse et à la formalisation de bases de travail. La prise de décision finale relève impérativement de la responsabilité humaine.

> [!CAUTION]
> Ne transmettez jamais de code source, d'identifiants techniques, de mots de passe ou de spécifications confidentielles aux outils d'IA.
> N'introduisez aucun nom de client, raison sociale, nom de collaborateur ou élément contractuel.
> Ne diffusez jamais directement les rapports d'incident, notes explicatives ou communications officielles générées par l'IA sans relecture, ajustement et validation par le management et, si nécessaire, la direction juridique.

---

## Use Case (Cas d'usage)

- Structurer l'analyse factuelle d'une anomalie majeure ou d'un incident de production.
- Distinguer rigoureusement les causes techniques directes (déclencheurs) des causes organisationnelles sous-jacentes (facteurs contributifs).
- Élaborer un plan d'actions préventives et correctives pour neutraliser la récurrence.
- Rédiger la trame d'un rapport d'incident ou d'une note de synthèse pour le client.
- Définir le plan d'amélioration interne des processus de développement et de qualification.

---

## Input (Informations à fournir à l'IA)

Après avoir chargé ce contexte, transmettez les informations ci-dessous (veillez à anonymiser rigoureusement les données techniques sensibles et nominatives) :

```
### Description de l'anomalie / Incident qualité constaté
(Synthèse factuelle des manifestations du problème. Exclure tout code source et identifiant technique)

### Circonstances de détection
(Quand, par qui, dans quel environnement et dans quelles conditions l'incident a été mis en évidence)

### Périmètre d'impact
(Fonctionnalités altérées, volumétrie ou profils d'utilisateurs touchés, processus métier impactés)

### Mesures conservatoires / Solutions de contournement immédiates (Workaround)
(Mesures d'urgence et palliatifs déjà déployés)

### Hypothèses causales identifiées
(Hypothèses techniques et fonctionnelles actuelles sur l'origine du dysfonctionnement)

### Processus de relecture & Revue par les pairs
(Modalités selon lesquelles les revues de conception et de code ont été conduites sur le périmètre)

### Dispositif et couverture de test
(Stratégie de test appliquée, types de tests exécutés, couverture et résultats lors de la recette)

### Risque de propagation / Récurrence
(Éléments laissant craindre que l'anomalie puisse affecter d'autres modules ou fonctionnalités)

### Impact Client & Utilisateur final
(Conséquences opérationnelles subies par le client ou les usagers, niveau de criticité perçu)
```

---

## Output (Livrables attendus de l'IA)

### 1. Caractérisation factuelle de l'incident
Synthèse chronologique de l'incident, de ses manifestations et des conditions de son identification.

### 2. Causes directes (Déclencheurs techniques)
Identification de la défaillance technique ou fonctionnelle immédiate à l'origine de l'anomalie.

### 3. Facteurs contributifs et causes profondes (Root Cause Analysis)
Analyse des défaillances sous-jacentes : gouvernance, exigences, processus de revue, environnement ou outillage.

### 4. Synthèse des mesures conservatoires
Bilan des actions d'urgence déployées, gains immédiats et limites opérationnelles associées.

### 5. Solution pérenne et plan de remédiation
Description des correctifs d'ingénierie nécessaires pour traiter définitivement la cause racine.

### 6. Plan de prévention et non-récurrence
Mesures correctives structurelles sur les processus, la qualité du code, les grilles de relecture, l'automatisation des tests et l'organisation.

### 7. Synthèse des impacts client
Évaluation objective des préjudices opérationnels et état de la relation client.

### 8. Plan d'amélioration interne
Axes de progrès identifiés pour l'équipe de réalisation et l'organisation d'ingénierie.

### 9. Trame de rapport d'incident (Post-Mortem / REX)
Structure type et arguments clés à intégrer dans la note de restitution destinée au client ou à la gouvernance.

---

## Caution (Précautions d'usage)

- **Ne diffusez jamais un rapport d'incident ou une communication de crise générée par l'IA sans validation managériale et juridique préalable.**
- Excluez impérativement tout extrait de code source, identifiant d'API, mot de passe ou architecture sensible.
- N'indiquez aucun nom de client, entreprise ou personne physique.
- Ne sollicitez jamais l'IA pour imputer la faute à un collaborateur ou désigner un responsable individuel.
- **Les livrables de l'IA ne valent pas arbitrage juridique ou contractuel.**

---

## Modèle de prompt standard

Copiez ce modèle, renseignez les données de l'incident et soumettez la requête :

```text
Sur la base des contextes de référence ci-dessous, analysez cet incident qualité et proposez les mesures correctives selon une perspective Chef de Projet.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de QUALITY_ISSUE_CONTEXT.md]

---

## Fiche incident qualité (Données anonymisées)

### Description de l'anomalie / Incident qualité constaté
(Renseigner)

### Circonstances de détection
(Renseigner)

### Périmètre d'impact
(Renseigner)

### Mesures conservatoires
(Renseigner)

### Hypothèses causales identifiées
(Renseigner)

### Processus de relecture
(Renseigner)

### Dispositif et couverture de test
(Renseigner)

### Risque de propagation / Récurrence
(Renseigner)

### Impact Client & Utilisateur final
(Renseigner)

---

## Livrables attendus

1. Caractérisation factuelle de l'incident
2. Causes directes
3. Facteurs contributifs et organisationnels
4. Synthèse des mesures conservatoires
5. Solution pérenne et plan de remédiation
6. Plan de prévention et non-récurrence (processus, revues, tests, organisation)
7. Synthèse des impacts client
8. Plan d'amélioration interne
9. Trame de rapport d'incident pour le client et le management

※ Tout projet de communication ou de rapport d'incident doit impérativement être validé par un humain, le management et les services compétents.
※ Les sorties de l'IA constituent une base de travail : l'arbitrage et la validation finale relèvent exclusivement de l'humain.
```

---

## Version structurée pour Claude (Format balises XML)

Pour une utilisation avec Claude, la structure balisée suivante garantit une restitution rigoureuse :

```text
<task>
Analysez l'incident qualité ci-dessous avec une perspective Chef de Projet : caractérisation des faits, analyse causale, mesures palliatives, solution pérenne, plan de non-récurrence et projet de note de synthèse.
</task>
<context>
<pm_context>
[Coller ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Coller ici le contenu de QUALITY_ISSUE_CONTEXT.md]
</specific_context>
</context>
<input>
【Fiche incident qualité (Données anonymisées)】

### Description de l'anomalie / Incident qualité constaté
(Renseigner)

### Circonstances de détection
(Renseigner)

### Périmètre d'impact
(Renseigner)

### Mesures conservatoires
(Renseigner)

### Hypothèses causales identifiées
(Renseigner)

### Processus de relecture
(Renseigner)

### Dispositif et couverture de test
(Renseigner)

### Impact Client & Utilisateur final
(Renseigner)
</input>
<constraints>
- Traitez l'ensemble des éléments comme strictement anonymisés (noms propres, raisons sociales et données contractuelles exclus).
- Si vous complétez des informations manquantes, mentionnez expressément « (Hypothèse) ».
- Ne mentionnez aucun engagement formel de responsabilité, indemnisation ou compensation financière.
- Précisez formellement que le projet de rapport d'incident requiert l'arbitrage du management et du département juridique.
- Formulez les réponses sous forme d'aide à la décision, l'arbitrage final revenant au responsable humain.
</constraints>
<output_format>
1. Caractérisation factuelle de l'incident
2. Causes directes et facteurs contributifs profonds
3. Synthèse des mesures conservatoires
4. Solution pérenne et plan de remédiation
5. Plan de prévention et non-récurrence
6. Synthèse des impacts client
7. Trame de rapport d'incident (Post-Mortem) pour le client et le management
</output_format>
```
