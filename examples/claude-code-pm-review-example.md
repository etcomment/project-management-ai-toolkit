# Utilisation de la compétence de revue PM dans Claude Code — Exemple pratique

## Cas d'usage (Use Case)

Ce scénario illustre l'utilisation de Claude Code pour réaliser un audit méthodologique sous l'angle du management de projet (PM) à partir des fichiers présents dans le dépôt du projet (README, backlog d'Issues, notes d'avancement, fiches de spécifications).

Le modèle exploite les directives de `.claude/skills/pm-review/SKILL.md` pour ausculter l'état réel d'avancement et les risques opérationnels.

> **Avertissement :** Cet exemple fournit des modèles de prompts pour Claude Code. Il ne comporte aucun hook, aucune commande d'automatisation, aucune configuration MCP, aucun commit automatique et aucun mécanisme de déploiement automatisé.

---

## Fichiers de contexte utilisés

- `.claude/skills/pm-review/SKILL.md`
- `contexts/PM_CONTEXT.md`

---

## Données d'entrée anonymisées (Sanitized Input)

> **Avertissement :** Les données ci-dessous sont entièrement fictives. Aucun nom réel de client, de projet ou d'individu n'est mentionné.

**Extrait du README fictif du dépôt de développement :**

```
# Dépôt de développement - Projet Alpha

## Présentation du projet
Développement d'un progiciel interne de gestion opérationnelle.
Phase 1 : modules d'administration, reporting analytique et interfaces externes.

## Phase actuelle
Milieu de phase de développement (70% d'avancement global)

## Prochaine échéance de mise en production
Fin de la Semaine 14 (délai restant : 3,5 semaines)
```

**Extrait du backlog fictif des Issues GitHub :**

```
Issue #12 : Module flux externes - Développement nominal achevé
  - Statut : Clôturée
  - Responsable : Développeur référent

Issue #18 : Module flux externes - Recette unitaire
  - Statut : Ouverte
  - Responsable : Développeur référent
  - Échéance : Non renseignée

Issue #21 : Élaboration du plan de conception des tests
  - Statut : Ouverte
  - Responsable : Non assigné
  - Échéance : Fin de semaine courante

Issue #24 : Tests d'intégration (interfaçage avec système partenaire)
  - Statut : Non démarrée
  - Responsable : Non assigné
  - Échéance : Non définie

Issue #27 : Comité de validation Go/No-Go - Fixation de la date
  - Statut : Non démarrée
  - Responsable : Non assigné
  - Échéance : Non définie

Issue #30 : Déploiement du registre de suivi des anomalies (Bug Tracker)
  - Statut : Non démarrée
  - Responsable : Non assigné
  - Échéance : Non définie
```

**Notes d'avancement (extraits) :**

```
Semaine 10 - Notes d'avancement interne :
- Le socle de code des flux externes est finalisé
- Les tests unitaires ne sont pas encore exécutés
- Rédacteur du plan de tests enfin désigné cette semaine. Démarrage prévu
- Plus que 3,5 semaines avant la mise en production. Forte tension sur les délais
- Le client pousse des demandes d'évolution (export groupé, etc.) : arbitrage non tranché
```

**Spécifications techniques (extraits) :**

```
Spécifications des flux de données v1.1 (Validées) :
- Rubrique X : déscopée de cette version
- Rubrique Y : intégration simplifiée (note de cadrage client en attente de réception)
- Rubrique Z : maintien des spécifications nominales
```

**Points en attente de retour client (Blockers) :**

```
- Note de cadrage détaillée sur la rubrique Y (toujours non reçue)
- Hiérarchisation et accord budgétaire sur les demandes additionnelles (export groupé)
- Date ferme du comité Go/No-Go de mise en production
```

**Contrainte d'échéance :**

```
Fin de la Semaine 14 (3,5 semaines restantes)
Date annoncée en interne par la direction du client : décalage calendaire proscrit
```

---

## Modèles de Prompts

Exemples d'instructions à soumettre à Claude Code :

### Version standard

```text
Après avoir analysé les directives de .claude/skills/pm-review/SKILL.md et de contexts/PM_CONTEXT.md,
réalise un audit méthodologique de l'état d'avancement de ce projet sous l'angle du management de projet.

Périmètre analysé :
- Ce fichier README
- La liste des Issues
- Les notes d'avancement
- Les notes de spécifications
- Les points en attente de retour client

Structure ton analyse selon les axes suivants :
1. Synthèse de situation
2. Niveau de criticité (Faible / Modéré / Élevé / Critique)
3. Principaux risques projet
4. Points de contrôle immédiats pour le Chef de Projet
5. Clarifications et arbitrages à obtenir du client
6. Décisions managériales internes à trancher
7. Plan d'actions prioritaires
```

### Version structurée en balises XML (recommandée pour Claude)

```text
<task>
Après avoir analysé les directives de .claude/skills/pm-review/SKILL.md et de contexts/PM_CONTEXT.md,
réalise un audit méthodologique de l'état d'avancement de ce projet sous l'angle du management de projet.
</task>
<input>
Périmètre analysé :
- Ce fichier README
- La liste des Issues
- Les notes d'avancement
- Les notes de spécifications
- Les points en attente de retour client
</input>
<constraints>
- N'affirme aucun fait qui ne soit explicitement étayé par les données d'entrée.
- Qualifie expressément toute déduction non vérifiée de « (Hypothèse / Conlecture) ».
- Ne formule aucun engagement définitif sur les délais, les coûts ou les responsabilités juridiques.
- Rappelle que cette restitution constitue une aide à la décision soumise à validation humaine préalable.
</constraints>
<output_format>
1. Synthèse de situation
2. Niveau de criticité (Faible / Modéré / Élevé / Critique) et justification
3. Principaux risques projet
4. Points de contrôle immédiats pour le Chef de Projet
5. Clarifications et arbitrages à obtenir du client
6. Décisions managériales internes à trancher
7. Plan d'actions prioritaires
</output_format>
```

---

## Livrable attendu de l'IA (Expected Output)

Exemple illustratif de la restitution attendue. Les résultats réels varient selon le modèle et les données injectées.

---

### 1. Synthèse de situation

Le Projet Alpha affiche 70% d'avancement théorique au milieu du développement. Si l'écriture du code des flux externes est terminée, la recette unitaire et les tests d'intégration restent à faire. Le plan de tests vient seulement d'être pris en charge alors que l'échéance finale est dans 3,5 semaines, créant un risque majeur d'écrasement de la phase de qualification. Plusieurs points bloquants client (spécifications de Y, arbitrage des demandes d'évolution, date du comité Go/No-Go) restent ouverts.

---

### 2. Niveau de criticité

**Élevé (High)**

- L'enchaînement conception des tests → recette unitaire → tests d'intégration → homologation → Go/No-Go doit être réalisé en 3,5 semaines
- Plusieurs Issues fondamentales n'ont ni responsable ni date butoir
- Des prérequis techniques et de cadrage client demeurent non résolus

---

### 3. Principaux risques projet

| # | Risque | Justification opérationnelle |
|---|---|---|
| 1 | Compression de la fenêtre de qualification | Le plan de tests démarre à peine ; les étapes de recette risquent d'être bâclées pour tenir la date |
| 2 | Carence de pilotage sur les Issues clés | Les Issues #21, #24, #27 et #30 n'ont pas de responsable ou d'échéance fixée |
| 3 | Blocages décisionnels côté client | Flou persistant sur la note Y, les demandes d'évolution et la date du comité décisionnel |
| 4 | Dérive de périmètre non maîtrisée | Demandes d'export groupé non arbitrées risquant de polluer le sprint final |
| 5 | Défaut de gestion de la qualité | Absence de registre centralisé des anomalies à la veille des tests |

---

### 4. Points de contrôle immédiats pour le Chef de Projet

- Verrouiller l'assignation et la date d'achèvement de l'Issue #21 (plan de tests)
- Affecter un responsable et une échéance sur les Issues #24 (intégration), #27 (Go/No-Go) et #30 (Bug Tracker)
- Valider avec la direction la posture vis-à-vis des demandes d'évolution
- Réévaluer le rétroplanning global pour vérifier la faisabilité physique des 3,5 semaines

---

### 5. Clarifications et arbitrages à obtenir du client

- Date ferme d'envoi de la note de cadrage sur la rubrique Y
- Confirmation formelle du report des demandes d'évolution à une version ultérieure
- Fixation de la date du comité de décision Go/No-Go de mise en production

---

### 6. Décisions managériales internes à arbitrer

- Décision d'arbitrage sur l'acceptation ou le refus des évolutions et tarification éventuelle
- Dispositif de repli si la durée de test s'avère insuffisante (renfort temporaire ou allègement ciblé)
- Validation des modalités et de l'outil de gestion des anomalies

---

### 7. Plan d'actions prioritaires

| Priorité | Action opérationnelle | Responsable |
|---|---|---|
| **P1 - Critique** | Assignation ferme et échéance sur l'Issue #21 (plan de tests) | Chef de Projet |
| **P1 - Critique** | Recalcul du rétroplanning détaillé de qualification | Chef de Projet / Lead Tech |
| **P2 - Haute** | Relance formelle du client sur la date du comité Go/No-Go | Chef de Projet |
| **P2 - Haute** | Arbitrage interne de direction sur les demandes d'évolution | Chef de Projet |
| **P2 - Haute** | Relance sur la note technique Y | Chef de Projet |
| **P3 - Moyenne** | Cadrage des Issues #24 et #30 | Chef de Projet |
| **P3 - Moyenne** | Déploiement du registre de suivi des anomalies | Lead Tech |

---

## Points de contrôle humain (Human Review Points)

Avant toute prise de décision, contrôlez impérativement :

- La conformité de l'analyse avec la réalité concrète de votre environnement de travail
- La justesse de la qualification de criticité au regard des marges de négociation avec le client
- La faisabilité réelle de l'ordonnancement des actions prioritaires
- La prise en compte des éléments non écrits (dynamique d'équipe, sensibilité politique du client)
- La mise à jour nominative des acteurs réels dans les plans d'actions

---

## Consignes de sécurité et avertissements (Caution)

> [!IMPORTANT]
> Les données de cet exemple sont purement fictives.
>
> Anonymisez l'intégralité des informations sensibles avant de solliciter un modèle d'IA.
>
> **L'IA ne prend pas de décisions opérationnelles ou contractuelles.** Tout engagement de délai, de budget ou de périmètre requiert la décision d'un responsable humain.
>
> Lors de l'utilisation de Claude Code, veillez à ne jamais configurer de hooks exécutables, de commandes non vérifiées ou de mécanismes d'action automatisés non supervisés.
