# Contexte de réunion hebdomadaire d'avancement / Weekly Meeting Context

---

## Purpose (Objectif de ce contexte)

Ce contexte structure la préparation et le suivi des réunions hebdomadaires d'avancement (points de synchronisation interne ou comités opérationnels clients). Il fournit un cadre méthodologique pour bâtir un ordre du jour équilibré, prioriser l'examen des sujets, identifier les prérequis de préparation et consolider le plan d'actions (relevé de décisions / TODO) post-réunion.

**L'IA ne remplace pas l'arbitrage du chef de projet.** L'IA est un outil de structuration, de cadrage des ordres du jour et de formalisation des plans d'action. La prise de décision finale relève impérativement de la responsabilité humaine.

> [!CAUTION]
> Ne transmettez aucun nom de client, raison sociale, nom de collaborateur ou élément contractuel confidentiel aux outils d'IA.
> Substituez systématiquement les données sensibles par des rôles et des dénominations génériques.

---

## Use Case (Cas d'usage)

- Préparer l'ordre du jour (agenda) d'un point hebdomadaire client ou interne.
- Déterminer le séquençage optimal des échanges et le calibrage du temps de parole (Timeboxing).
- Établir la revue d'avancement des actions actées lors de la séance précédente.
- Consolider le plan d'actions opérationnel (relevé de décisions / TODO) immédiatement après la séance.
- Identifier en amont les risques et arbitrages sensibles à mettre sur la table.

---

## Input (Informations à fournir à l'IA)

Après avoir chargé ce contexte, transmettez les informations ci-dessous (veillez à anonymiser rigoureusement les données confidentielles et nominatives) :

```
### Finalité de la réunion
(ex. : Point hebdomadaire d'avancement avec le client, synchronisation interne de l'équipe de développement)

### Rôles des participants (aucun nom réel)
(ex. : PM, Lead Dev, Ingénieur DevOps, Référent Fonctionnel Client A, etc.)

### Avancement opérationnel
(Synthèse des travaux achevés, en cours et en retard sous forme de puces)

### Points durs et blocages à instruire
(Difficultés techniques, fonctionnelles ou organisationnelles à trancher en séance)

### Demandes d'arbitrage client (en cas de point client)
(Questions ouvertes nécessitant un arbitrage ou une validation formelle du client)

### Actions en suspens de la séance précédente
(État d'avancement des engagements et tâches actés lors du précédent point)

### Objectifs d'arbitrage de la séance
(Décisions impératives devant être formellement arrêtées au terme de la réunion)

### Durée planifiée (en minutes)
(ex. : 45 min, 60 min, 90 min)
```

---

## Output (Livrables attendus de l'IA)

### 1. Ordre du jour de la réunion (Agenda)

| N° | Sujet / Thématique | Objectif visé | Durée estimée | Porteur (Rôle) |
|---|---|---|---|---|

### 2. Séquençage et allocation du temps (Timeboxing)
Hiérarchisation des priorités d'instruction et recommandations de cadencement pour tenir la durée impartie.

### 3. Checklist de préparation en amont
Inventaire des éléments à réunir avant la séance : indicateurs, démonstrations, documents de cadrage ou pré-alignements.

### 4. Revue des actions antérieures
Grille de suivi des engagements pris lors de la séance précédente pour s'assurer du débouclage effectif.

### 5. Relevé d'actions et décisions (TODO post-réunion)

| N° | Intitulé de l'action / Décision | Responsable (Rôle) | Échéance | Remarques & Critères d'acceptation |
|---|---|---|---|---|

### 6. Points reportés / Ajournements
Identification des questions n'ayant pu être tranchées et nécessitant une séance ad hoc ou une instruction complémentaire.

### 7. Risques critiques à instruire en séance
Identification des risques émergents à partager impérativement lors du point d'étape.

---

## Caution (Précautions d'usage)

- **Ne saisissez aucun nom réel de client, de société ou d'individu.** Utilisez des rôles génériques (« Représentant Client A », « PM »).
- L'ordre du jour généré est un cadre de travail : adaptez-le à la dynamique réelle de vos interlocuteurs.
- Ne diffusez jamais un ordre du jour ou un compte rendu au client sans vérification et validation par le chef de projet.
- **Les livrables de l'IA ne valent pas procès-verbal contractuel.**

---

## Modèle de prompt standard

Copiez ce modèle, renseignez les éléments de cadrage de la réunion et soumettez la requête :

```text
Sur la base des contextes de référence ci-dessous, élaborez l'ordre du jour et la checklist de préparation de notre point hebdomadaire selon une perspective Chef de Projet.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de WEEKLY_MEETING_CONTEXT.md]

---

## Cadrage de la réunion (Données strictement anonymisées)

### Finalité de la réunion
(Renseigner)

### Rôles des participants (aucun nom réel)
(Renseigner)

### Avancement opérationnel
(Renseigner)

### Points durs et blocages à instruire
(Renseigner)

### Demandes d'arbitrage client
(Renseigner)

### Actions en suspens de la séance précédente
(Renseigner)

### Objectifs d'arbitrage de la séance
(Renseigner)

### Durée planifiée
(Renseigner)

---

## Livrables attendus

1. Ordre du jour (Sujet, Objectif, Durée, Porteur)
2. Séquençage et timeboxing recommandé
3. Checklist de préparation en amont
4. Revue des actions de la séance précédente
5. Trame du relevé d'actions post-réunion (TODO)
6. Traitement des points potentiellement ajournés
7. Risques critiques à partager en séance

※ Les sorties constituent une base de travail : validation humaine obligatoire avant toute communication.
```

---

## Version structurée pour Claude (Format balises XML)

Pour une utilisation avec Claude, la structure balisée suivante garantit une parfaite délimitation des consignes :

```text
<task>
Sur la base des informations ci-dessous, structurez l'ordre du jour et la préparation de la réunion hebdomadaire d'avancement.
</task>
<context>
<pm_context>
[Coller ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Coller ici le contenu de WEEKLY_MEETING_CONTEXT.md]
</specific_context>
</context>
<input>
【Cadrage de la réunion (Données strictement anonymisées)】

### Finalité de la réunion
(Renseigner)

### Rôles des participants (aucun nom réel)
(Renseigner)

### Avancement opérationnel
(Renseigner)

### Points durs et blocages à instruire
(Renseigner)

### Demandes d'arbitrage client
(Renseigner)

### Actions en suspens de la séance précédente
(Renseigner)

### Objectifs d'arbitrage de la séance
(Renseigner)

### Durée planifiée
(Renseigner)
</input>
<constraints>
- Considérez l'ensemble des participants et organisations comme strictement anonymisés.
- Mentionnez « (Hypothèse) » pour tout élément complété par déduction.
- Le livrable constitue un support préparatoire devant impérativement être validé par le chef de projet avant diffusion.
</constraints>
<output_format>
1. Ordre du jour (Thématique, Objectif, Durée, Porteur)
2. Séquençage et cadrage temporel (Timeboxing)
3. Checklist des éléments à réunir avant séance
4. Revue des engagements de la séance précédente
5. Trame du plan d'actions (Relevé de décisions / TODO)
6. Identification des points d'ajournement probables
7. Risques majeurs à instruire en séance
</output_format>
```
