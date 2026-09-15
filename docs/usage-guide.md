# Guide d'utilisation / Usage Guide

---

## Introduction

Le présent dépôt « project-management-ai-toolkit » est une boîte à outils méthodologique conçue pour permettre aux chefs de projet (PM), PMO et leaders techniques d'exploiter la puissance de ChatGPT, Gemini, Claude et Claude Code dans leurs missions quotidiennes de pilotage.

Ce guide explicite les modalités d'utilisation du dépôt et la sélection des fichiers selon vos objectifs opérationnels.

---

## Processus d'utilisation

```
[1] Consulter le README
        │
        v
[2] Vérifier le DISCLAIMER et le guide ai-safety
        │
        v
[3] Prendre connaissance de PM_CONTEXT.md
        │
        v
[4] Sélectionner le fichier contexts/*.md adapté à votre besoin
        │
        ├─ Rapport d'avancement     → STATUS_REPORT_CONTEXT.md
        ├─ Incidents & Risques      → ISSUE_RISK_CONTEXT.md
        ├─ Restitution Client       → CLIENT_COMMUNICATION_CONTEXT.md
        ├─ Gestion de crise (72h)   → FIRE_RESPONSE_FIRST_72H.md
        └─ Autres cas d'usage       → Se référer au tableau ci-dessous
        │
        v
[5] Anonymiser et masquer les données du projet
        │
        v
[6] Soumettre la requête à l'IA
        │
        v
[7] Relire, ajuster et valider humainement le résultat
```

> [!IMPORTANT]
> Les sorties de l'IA ne remplacent en aucun cas l'arbitrage managérial ou légal. Tout livrable doit impérativement être relu, vérifié et validé par un responsable humain.
> Ne saisissez jamais d'informations confidentielles, de données personnelles ou d'identifiants techniques dans les services d'IA.

---

## Fichiers fondamentaux à lire en priorité

| Fichier | Objet |
|---|---|
| [README.md](../README.md) | Présentation générale du référentiel et démarrage rapide (Quick Start) |
| [docs/legal/DISCLAIMER.md](legal/DISCLAIMER.md) | Clause de non-responsabilité, limites opérationnelles de l'IA et règles de confidentialité |
| [docs/ai-safety.md](ai-safety.md) | Données autorisées, exemples d'entrées proscrites et bonnes pratiques de sécurité |
| [contexts/PM_CONTEXT.md](../contexts/PM_CONTEXT.md) | Socle commun et cadre de référence méthodologique des pratiques PM |

---

## Sélection des fichiers par cas d'usage

Pour identifier en un coup d'œil le fichier correspondant à votre situation actuelle, consultez [docs/use-case-map.md](use-case-map.md).

| Objectif visé | Fichier de contexte associé |
|---|---|
| Réaliser le bilan de santé 360° du projet (Health Check) | `contexts/PROJECT_HEALTH_CHECK.md` |
| Rédiger le rapport d'avancement périodique | `contexts/STATUS_REPORT_CONTEXT.md` |
| Structurer le registre des incidents et des risques | `contexts/ISSUE_RISK_CONTEXT.md` |
| Préparer une note d'explication ou d'arbitrage pour le client | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| Gérer les premières 72h d'une crise opérationnelle majeure | `contexts/FIRE_RESPONSE_FIRST_72H.md` |
| Transformer des notes de réunion en compte rendu et plan d'actions (TODO) | `contexts/MEETING_MINUTES_CONTEXT.md` |
| Établir l'ordre du jour d'une réunion hebdomadaire (Timeboxing) | `contexts/WEEKLY_MEETING_CONTEXT.md` |
| Analyser l'impact d'un changement de périmètre (Scope Change) | `contexts/SCOPE_CHANGE_CONTEXT.md` |
| Concevoir un plan de rattrapage face à une dérive calendaire | `contexts/DELAY_RECOVERY_CONTEXT.md` |
| Instruire l'analyse causale et le plan d'action d'un incident qualité | `contexts/QUALITY_ISSUE_CONTEXT.md` |
| Conduire une rétrospective Agile ou un post-mortem (REX) | `contexts/RETROSPECTIVE_CONTEXT.md` |
| Cadrer le reporting stratégique destiné aux décideurs | `contexts/STAKEHOLDER_REPORT_CONTEXT.md` |
| Formaliser les hypothèses de chiffrage et l'analyse d'incertitude | `contexts/ESTIMATION_CONTEXT.md` |
| Mener une revue transversale de portefeuille multi-projets PMO | `contexts/PMO_REVIEW_CONTEXT.md` |
| Structurer une remontée d'alerte technique vers le chef de projet | `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md` |

---

## Typologie des ressources

### Fiches de contexte opérationnelles (Contexts)

Les fichiers situés sous `contexts/` forment le cœur universel de la boîte à outils. Chaque fichier intègre :

- Purpose (Objectif)
- Use Case (Cas d'usage)
- Input (Données à fournir)
- Output (Livrables attendus)
- Caution (Précautions d'usage)
- Exemples d'utilisation (Requêtes types prêtes à l'emploi)

### Fichiers de configuration (Instructions)

Gabarits de prompts système destinés à être configurés directement dans vos interfaces d'IA, situés sous `instructions/` :

| Fichier | Destination |
|---|---|
| `instructions/chatgpt-project-instructions.md` | Paramètres Instructions de ChatGPT Projects |
| `instructions/custom-gpt-instructions.md` | Champ Instructions des Custom GPTs de ChatGPT |
| `instructions/gemini-instructions.md` | Champ Instructions des Gems de Google Gemini |
| `instructions/claude-project-instructions.md` | Instructions de projet de Claude Projects |

### Guides d'outillage pour l'utilisateur

Les documents regroupés sous `docs/tools/` fournissent des guides pas à pas pour chaque plateforme.

---

## Modalités d'utilisation par plateforme d'IA

### ChatGPT

- Collez le contenu du fichier de contexte souhaité dans la conversation, suivi des données anonymisées de votre projet.
- Pour gagner en efficacité, configurez `instructions/chatgpt-project-instructions.md` dans votre projet ChatGPT.
- Guide détaillé : [docs/tools/chatgpt.md](tools/chatgpt.md)

### Gemini

- Collez le fichier de contexte en préambule de votre invite dans Gemini.
- Pour configurer un Gem personnalisé, appuyez-vous sur `instructions/gemini-instructions.md`.
- Guide détaillé : [docs/tools/gemini.md](tools/gemini.md)

### Claude

- Configurez les instructions de projet dans Claude Projects à l'aide de `instructions/claude-project-instructions.md`.
- Pour les contextes volumineux, épurez les informations non indispensables avant soumission.
- Guide détaillé : [docs/tools/claude.md](tools/claude.md)

### Claude Code

- Dispose d'un ensemble de compétences dédiées regroupées sous `.claude/skills/`.
- Permet d'auditer les README, backlogs d'issues et spécifications directement en ligne de commande sous l'angle PM.
- Ne comporte aucun hook ni script d'exécution automatique non sollicité.
- Guide détaillé : [docs/tools/claude-code.md](tools/claude-code.md)

---

## Protocole d'anonymisation avant transmission à l'IA

Avant de soumettre la moindre information relative à un projet, appliquez rigoureusement les étapes suivantes :

### Étape 1. Contrôle d'éligibilité des données

- Vérifier l'absence absolue de données clients nominatives, coordonnées personnelles, clauses contractuelles confidentielles ou identifiants.
- S'assurer que les informations ne sont pas couvertes par un accord de confidentialité (NDA) strict ou des politiques internes interdisant l'usage de services tiers.

### Étape 2. Masquage et pseudonymisation

| Donnée réelle (Exemple) | Donnée anonymisée à saisir |
|---|---|
| Société Alpha (Nom du client) | Client A |
| Jean Dupont (Chef de projet client) | Intervenant A / Responsable Client |
| api_key_xxxxxxxxxx | [SUPPRIMÉ] |
| Montant du contrat : 350 000 € | Budget : Ordre de grandeur de plusieurs centaines de k€ |

### Étape 3. Synthèse et abstraction

Si la mention de chiffres ou de métriques précises n'est pas indispensable à l'analyse, remplacez-les par des tendances qualitatives ou des ordres de grandeur macroscopiques.

---

## Architecture générale du référentiel

```
project-management-ai-toolkit/
├── README.md
├── LICENSE.md
├── .gitignore
│
├── contexts/                          ← Fiches de contexte méthodologiques (Composant central)
│   ├── PM_CONTEXT.md
│   ├── PROJECT_HEALTH_CHECK.md
│   ├── STATUS_REPORT_CONTEXT.md
│   ├── ISSUE_RISK_CONTEXT.md
│   ├── FIRE_RESPONSE_FIRST_72H.md
│   ├── CLIENT_COMMUNICATION_CONTEXT.md
│   ├── MEETING_MINUTES_CONTEXT.md
│   ├── WEEKLY_MEETING_CONTEXT.md
│   ├── SCOPE_CHANGE_CONTEXT.md
│   ├── DELAY_RECOVERY_CONTEXT.md
│   ├── QUALITY_ISSUE_CONTEXT.md
│   ├── RETROSPECTIVE_CONTEXT.md
│   ├── STAKEHOLDER_REPORT_CONTEXT.md
│   ├── ESTIMATION_CONTEXT.md
│   ├── PMO_REVIEW_CONTEXT.md
│   └── ENGINEER_TO_PM_REPORT_CONTEXT.md
│
├── instructions/                      ← Instructions de configuration système prêtes à l'emploi
│   ├── chatgpt-project-instructions.md
│   ├── custom-gpt-instructions.md
│   ├── gemini-instructions.md
│   └── claude-project-instructions.md
│
├── examples/                          ← Exemples d'application sur données fictives
│   ├── README.md
│   ├── project-health-check-example.md
│   ├── status-report-example.md
│   ├── issue-risk-review-example.md
│   ├── meeting-minutes-example.md
│   ├── fire-response-first-72h-example.md
│   ├── scope-change-example.md
│   ├── delay-recovery-example.md
│   └── claude-code-pm-review-example.md
│
├── docs/
│   ├── usage-guide.md                 ← Présent guide d'utilisation
│   ├── ai-safety.md
│   ├── use-case-map.md
│   ├── github-publishing-checklist.md
│   ├── tools/
│   │   ├── chatgpt.md
│   │   ├── gemini.md
│   │   ├── claude.md
│   │   └── claude-code.md
│   ├── legal/
│   │   ├── DISCLAIMER.md
│   │   └── TERMS.md
│   └── meta/
│       ├── CHANGELOG.md
│       └── ROADMAP.md
│
├── .claude/
│   └── skills/
│       ├── pm-review/SKILL.md
│       ├── project-health-check/SKILL.md
│       ├── status-report/SKILL.md
│       ├── issue-risk-review/SKILL.md
│       ├── client-communication/SKILL.md
│       ├── fire-response-first-72h/SKILL.md
│       ├── meeting-minutes/SKILL.md
│       ├── scope-change-review/SKILL.md
│       └── delay-recovery/SKILL.md
│
└── .github/
    ├── CONTRIBUTING.md
    ├── SECURITY.md
    ├── pull_request_template.md
    └── ISSUE_TEMPLATE/
```

---

## Prise en main par les exemples

Pour visualiser des cas concrets de requêtes, de données saisies et de restitutions attendues, consultez le répertoire `examples/`.

> [!IMPORTANT]
> L'intégralité des exemples repose sur des données strictement fictives. Ils ne comportent aucune référence à des clients, projets ou personnes réels.
> Les livrables de l'IA ne remplacent en aucun cas l'arbitrage managérial et doivent être validés par un responsable humain.

---

## Éditeur du projet

Ce référentiel est édité et maintenu par TechAide Inc.

https://techaide.jp/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit
