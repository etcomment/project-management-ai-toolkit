# Contexte de bilan de santé projet / Project Health Check Context

---

## Purpose (Objectif de ce contexte)

Ce contexte fournit une grille de lecture multidimensionnelle pour évaluer l'état de santé opérationnel d'un projet sous l'angle du pilotage (PM/PMO).

En transmettant à l'IA les éléments d'avancement, points de blocage, risques, dynamique client, capacité de l'équipe et indicateurs de qualité, vous disposez d'un appui d'analyse pour détecter les angles morts, biais de perception et signaux faibles de dérive.

**L'IA ne réalise ni audit formel ni certification de projet.** Les résultats constituent une aide à l'analyse : ils doivent être rigoureusement confrontés au terrain et validés par le chef de projet.

---

## Use Case (Cas d'usage)

- Réaliser une revue périodique à 360° de la santé globale du projet.
- Objectiver, formuler et structurer un sentiment diffus de dérive ou d'inquiétude.
- Préparer les revues d'avancement mensuelles ou hebdomadaires.
- Structurer le dossier de cadrage avant un point d'étape avec la direction ou le client.
- Détecter les signaux précurseurs d'une crise ou d'un dérapage projet.

---

## Input (Informations à fournir à l'IA)

Après avoir chargé ce contexte, transmettez les éléments ci-dessous (veillez à anonymiser rigoureusement les données confidentielles et nominatives).

Ces rubriques ne sont pas toutes obligatoires, mais la pertinence de l'analyse dépend directement de la complétude des éléments fournis :

```
### Synthèse du projet
- Finalité et contexte du projet :
- Livrables majeurs :
- Phase actuelle : (ex. : Cadrage/Spécifications, Conception, Développement, Recette/Qualification, Déploiement)
- Calendrier directeur / Jalons clés (anonymisé) :
- Envergure / Périmètre : (ex. : Petit, Moyen, Grand projet)

### Avancement réel
- Taux d'avancement global (%) :
- Réalisations / Tâches achevées sur la période (semaine/mois) :
- Statut de franchissement des jalons :
- Tâches ou chantiers en retard (le cas échéant) :

### Points de blocage (Issues)
- Incidents / Bloquants actifs (utiliser des rôles ou alias : « Développeur A ») :
- Points ouverts non arbitrés :
- Tâches sans responsable identifié :
- Points d'action sans échéance explicite :

### Registre des risques
- Risques majeurs identifiés :
- Dépendances externes (attente d'arbitrage client, validation de tiers, livraison d'API partenaire, etc.) :
- Risques sans plan de contingence ni stratégie de mitigation :

### Contexte Client & Parties Prenantes
- Décisions / Validations en attente côté client :
- Disponibilité et posture de l'équipe cliente (nommer « Représentant Client A ») :
- Exigences, attentes fortes ou irritants exprimés :
- Risques ou points d'attention dans la communication client :

### Équipe & Capacité opérationnelle
- Dimensionnement de l'équipe (par rôle opérationnel) :
- Tensions RH / Staffing (surcharge, charge/capacité, déficit d'expertise, congés/départs) :

### Qualité & Dette technique
- État des tests / qualification (campagnes en cours, volumétrie des anomalies bloquantes/majeures) :
- Risques ou dérives constatés sur la qualité des livrables :

### Faits marquants récents & Comptes rendus
- Synthèse des derniers comités ou échanges formels (noms et entités masqués) :
- Événements exceptionnels ou incidents survenus récemment :
```

---

## Output (Livrables attendus de l'IA)

Lorsque vous soumettez votre demande avec ce contexte, l'IA structure sa restitution selon les volets suivants :

### 1. Synthèse de situation
Condensé exécutif de la situation du projet en 3 à 5 phrases percutantes.

### 2. Niveau de criticité opérationnelle
Évaluation synthétique selon 4 niveaux :

| Niveau | Critères d'appréciation |
|---|---|
| 🔴 Critique (Action immédiate) | Risque imminent de rupture sur les délais, le budget, la qualité ou la relation client |
| 🟡 Sous vigilance (Attention requise) | Multiples signaux d'alerte ; dégradation probable sans intervention corrective rapide |
| 🟢 Nominal (Sous contrôle) | Difficultés ordinaires maîtrisées dans le cadre du pilotage courant |
| ⬜ Non déterminable | Données d'entrée insuffisantes pour poser un diagnostic fiable |

### 3. Points d'attention prioritaires
Hiérarchisation par ordre d'urgence des alertes et anomalies requérant un traitement immédiat.

### 4. Angles morts et risques sous-estimés
Mise en lumière des risques induits ou des zones de fragilité implicites non formalisées par l'équipe.

### 5. Demandes d'arbitrage à soumettre au Client
Liste des clarifications, validations et décisions à obtenir formellement du client.

### 6. Décisions internes à trancher
Arbitrages organisationnels, techniques ou budgétaires à acter en interne (PM, PMO, Direction).

### 7. Plan d'action à 24–72 heures
Plan d'actions prioritaires et opérationnelles pour reprendre la maîtrise sous 1 à 3 jours.

---

## Caution (Précautions d'usage)

> [!CAUTION]
> Les sorties générées à partir de ce contexte ne constituent en aucun cas un audit légal, une certification qualité ou un conseil d'expert habilité.
>
> Tout contenu doit impérativement être revu, validé et ajusté par un responsable humain avant d'être exploité ou communiqué.
>
> Ne saisissez aucune donnée confidentielle, nominative, contractuelle ou d'authentification dans les outils d'IA.

---

## Modèle de prompt standard

```text
# Demande de bilan de santé projet (Health Check)

En vous appuyant sur les contextes de référence ci-dessous, réalisez une revue de santé complète du projet selon une perspective Chef de Projet.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]

[Coller ici le contenu de PROJECT_HEALTH_CHECK.md]

---

## Données de situation du projet (Données strictement anonymisées)

### Synthèse du projet
- Finalité du projet :
- Phase actuelle :
- Calendrier directeur :

### Avancement
- Taux d'avancement global :
- Livrables achevés :
- Chantiers en retard :

### Points de blocage & Risques
- Incidents / Bloquants actifs :
- Risques majeurs identifiés :
- Arbitrages client en attente :

### Équipe & Qualité
- Tensions sur le staffing / charge :
- Alertes qualité / anomalies :

### Événements récents

---

## Livrables attendus

1. Synthèse de situation
2. Niveau de criticité (🔴 Critique / 🟡 Sous vigilance / 🟢 Nominal) et justification
3. Points d'attention prioritaires (par ordre de criticité)
4. Angles morts et risques sous-estimés
5. Demandes d'arbitrage à soumettre au Client
6. Décisions internes à trancher
7. Plan d'action à 24–72 heures

※ Les sorties constituent une base d'aide à la décision : l'arbitrage final revient exclusivement à un responsable humain.
```

---

## Version structurée pour Claude (Format balises XML)

Pour un traitement optimal avec Claude, utilisez la structure balisée suivante :

```text
<task>
Réalisez une revue de santé (Health Check) de la situation projet ci-dessous avec une perspective Chef de Projet.
Restituez le niveau de criticité, les points d'attention majeurs, les risques sous-estimés, les arbitrages client/internes et le plan d'action immédiat sous 24 à 72h.
</task>
<context>
<pm_context>
[Coller ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Coller ici le contenu de PROJECT_HEALTH_CHECK.md]
</specific_context>
</context>
<input>
【Données de situation du projet (Données strictement anonymisées)】

### Synthèse du projet
- Finalité du projet :
- Phase actuelle :
- Calendrier directeur :

### Avancement
- Taux d'avancement global :
- Livrables achevés :
- Chantiers en retard :

### Points de blocage & Risques
- Incidents / Bloquants actifs :
- Risques majeurs identifiés :
- Arbitrages client en attente :

### Équipe & Qualité
- Tensions sur le staffing / charge :
- Alertes qualité / anomalies :

### Événements récents
</input>
<constraints>
- Considérez les données fournies comme strictement anonymisées (noms propres, raisons sociales et données contractuelles exclus).
- Si vous complétez des informations manquantes, mentionnez expressément « (Hypothèse) ».
- En cas d'informations insuffisantes pour statuer, indiquez « Données insuffisantes » ou « Les éléments fournis ne permettent pas de trancher ».
- Formulez les réponses sous forme d'aide à la décision, l'arbitrage final revenant au responsable humain.
</constraints>
<output_format>
1. Synthèse de situation
2. Niveau de criticité (🔴 Critique / 🟡 Sous vigilance / 🟢 Nominal) et justification
3. Points d'attention prioritaires (par ordre de criticité)
4. Angles morts et risques sous-estimés
5. Demandes d'arbitrage à soumettre au Client
6. Décisions internes à trancher
7. Plan d'action à 24–72 heures
</output_format>
```
