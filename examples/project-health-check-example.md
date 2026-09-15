# Diagnostic de santé de projet (Project Health Check) — Exemple pratique

## Cas d'usage (Use Case)

Ce scénario illustre l'évaluation globale de l'état de santé d'un projet sous l'angle du management de projet (PM).

En phase intermédiaire de développement, le chef de projet formalise l'avancement, les points de blocage, les vulnérabilités de l'équipe et les risques qualité afin d'obtenir une revue critique et structurée par l'IA.

---

## Fichiers de contexte utilisés

- `contexts/PM_CONTEXT.md`
- `contexts/PROJECT_HEALTH_CHECK.md`

---

## Données d'entrée anonymisées (Sanitized Input)

> **Avertissement :** Les données ci-dessous sont entièrement fictives. Aucun nom réel de client, de projet ou d'individu n'est mentionné.

```
Projet : Projet Alpha (Fictif)
Phase : Milieu de phase de développement

【Avancement opérationnel】
- Avancement global : environ 60%
- Chantiers en retard : modules d'interfaçage externe, conception des plans de tests
- Les interfaces externes accusent 1,5 semaine de dérive par rapport au planning initial
- La conception des plans de tests n'a pas encore débuté

【Points de blocage et alertes (Issues)】
- Demande d'arbitrage sur les spécifications transmise au contact client A sans réponse depuis plus de 2 semaines
- Développement partiellement suspendu en raison de spécifications de flux d'échange de données non stabilisées
- Risque élevé de divergence d'interprétation entre les développeurs sur les interfaces backend (I/F)

【Vulnérabilités de l'équipe et de l'organisation】
- Une seule personne habilitée aux revues de code, mobilisée en parallèle sur d'autres tâches, entraînant un goulot d'étranglement
- Absence prévue du Lead Développeur pendant 3 jours la semaine prochaine

【Risques Qualité】
- Fenêtre de tests d'intégration limitée à 5 jours ouvrés dans le planning actuel
- Couverture des tests unitaires non consolidée
- Absence de registre centralisé de suivi des anomalies (Bug Tracker)

【Autres éléments de contexte】
- Délai restant avant mise en production (jalon final) : 6 semaines
- Date du comité de validation de mise en production (Go/No-Go) non fixée
```

---

## Prompt

```text
Après avoir intégré les fichiers de contexte ci-dessous, effectue une revue d'état de santé (health check) de la situation du projet avec la rigueur d'un chef de projet senior.

【Fichiers de contexte】
- contexts/PM_CONTEXT.md
- contexts/PROJECT_HEALTH_CHECK.md

【Données du projet】
(Coller les données d'entrée anonymisées ci-dessus)

Structure ton analyse selon les axes suivants :
1. Synthèse de situation
2. Niveau de criticité (Faible / Modéré / Élevé / Critique)
3. Principaux facteurs de vigilance
4. Risques latents et angles morts potentiels
5. Arbitrages et clarifications à obtenir du client
6. Décisions managériales internes à arbitrer
7. Plan d'actions immédiat pour les 24 à 72 prochaines heures
```

---

## Livrable attendu de l'IA (Expected Output)

Exemple illustratif de la restitution attendue. Les résultats réels varient selon le modèle et les données injectées.

---

### 1. Synthèse de situation

Le Projet Alpha a atteint 60% d'avancement au stade intermédiaire du développement. Des dérives sensibles se cumulent sur les interfaces externes et la conception des tests, aggravées par une absence de validation client depuis deux semaines et des spécifications non stabilisées. La concentration des revues sur une seule ressource et l'extrême brièveté des tests d'intégration (5 jours) font peser un risque qualité critique sur l'échéance des 6 semaines restantes.

---

### 2. Niveau de criticité

**Élevé (High)**

- Capacité de résorption des retards incertaine au regard du délai résiduel de 6 semaines
- Absence totale d'initialisation des plans de tests combinée à une phase de recette/intégration sous-dimensionnée
- Enlisement des arbitrages côté client bloquant les prérequis de développement

---

### 3. Principaux facteurs de vigilance

| # | Facteur d'alerte | Justification opérationnelle |
|---|---|---|
| 1 | Conception des tests non démarrée | Risque majeur d'impossibilité de concevoir, exécuter et corriger les anomalies dans les 6 semaines imparties |
| 2 | Arbitrage client en suspens depuis 2 semaines | Développer sur des hypothèses non validées expose à des retouches massives (rework) en phase aval |
| 3 | Goulot d'étranglement sur la revue (1 personne à temps partiel) | Cadence de revue inadaptée au flux de développement, générant latence et baisse de rigueur qualité |
| 4 | Spécifications des interfaces de données non figées | Cause première du retard sur les flux externes. Poursuivre sans cadrage strict risque de corrompre l'architecture |

---

### 4. Risques latents et angles morts potentiels

- Date de comité Go/No-Go non fixée : les critères d'acceptation et exigences de conformité risquent de ne pas être partagés à temps
- Absence de suivi formalisé des anomalies : perte de visibilité sur le volume et la sévérité des régressions lors des tests
- Absence de délégation formalisée pendant les 3 jours d'indisponibilité du Lead Tech, risquant de paralyser la prise de décision technique
- Calendrier d'alignement pour les tests de recette avec les systèmes tiers externes non synchronisé

---

### 5. Arbitrages et clarifications à obtenir du client

- Émettre une relance formelle avec date butoir impérative pour la validation des spécifications en attente
- Convenir du processus d'approbation expresse des formats d'échange de données
- Arrêter la date ferme et la grille d'acceptation du comité de validation de mise en production
- Vérifier la mise en place du dispositif de support et d'exploitation post-déploiement (gestion des incidents, canal d'escalade)

---

### 6. Décisions managériales internes à arbitrer

- Lancer immédiatement l'atelier de conception des plans de tests (démarrage sans délai)
- Réévaluer la durée des tests d'intégration (extension du calendrier ou recentrage du périmètre de test pour préserver le niveau d'exigence)
- Décharger la ressource en charge des revues de code ou adjoindre un pair pour débloquer le goulot d'étranglement
- Désigner formellement le suppléant habilité à arbitrer techniquement durant l'absence du Lead Tech
- Déployer immédiatement un tableau standardisé de gestion des anomalies

---

### 7. Plan d'actions immédiat pour les 24 à 72 prochaines heures

- [ ] Adresser un e-mail de relance assorti d'une échéance ferme au contact client A pour l'arbitrage des spécifications
- [ ] Arrêter la date de démarrage, l'affectation des ressources et le planning d'exécution des plans de tests
- [ ] Définir et communiquer à l'équipe la chaîne de délégation temporaire durant l'absence du Lead Développeur
- [ ] Engager la planification du comité Go/No-Go de mise en production
- [ ] Mettre à disposition le gabarit de suivi et de qualification des anomalies

---

## Points de contrôle humain (Human Review Points)

Préalablement à toute exploitation managériale de cette restitution, le chef de projet doit impérativement examiner :

- L'adéquation du niveau de criticité évalué avec la réalité du contexte contractuel et relationnel
- La pertinence des demandes adressées au client au regard des engagements contractuels et du climat partenarial
- La faisabilité réelle des arbitrages internes proposés compte tenu des moyens et de l'organisation de l'équipe
- Le réalisme du plan d'actions au regard des capacités d'absorption opérationnelles
- Les risques spécifiques ou contextuels non détectés par l'IA connus de vous seul

---

## Consignes de sécurité et avertissements (Caution)

> [!IMPORTANT]
> Cet exemple s'appuie exclusivement sur des données fictives. Aucun nom réel de client, de projet ou de collaborateur n'y est divulgué.
>
> Avant toute soumission d'informations à un modèle d'IA, veillez à anonymiser rigoureusement l'ensemble des données sensibles ou confidentielles.
>
> **Les livrables générés par l'IA ne remplacent pas le jugement professionnel.** Toute utilisation pour une communication client, une synthèse de direction, un engagement calendaire ou un chiffrage financier exige une validation humaine approfondie.
