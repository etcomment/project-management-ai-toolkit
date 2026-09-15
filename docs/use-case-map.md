# Cartographie des cas d'usage / Use Case Map

---

## Finalité de ce guide

Ce guide vous oriente vers les fichiers `contexts/*.md` adaptés à chaque situation opérationnelle de gestion de projet (PM).

- Utilisable indifféremment avec ChatGPT, Gemini, Claude et Claude Code.
- Ce guide est centré sur les fichiers de contexte du répertoire `contexts/`.
- Il n'existe pas de répertoire `prompts/` séparé : les modèles de requêtes et exemples concrets sont directement intégrés dans la section `Exemples d'utilisation (Requêtes types)` de chaque fichier `contexts/*.md`.
- Sélectionnez d'abord le fichier `contexts/*.md` correspondant à votre besoin, puis appuyez-vous sur sa section d'exemples pour calibrer votre consigne.

---

## Schéma d'orientation générale

```text
Besoin immédiat
│
├─ Évaluer la santé globale du projet
│    └─ contexts/PROJECT_HEALTH_CHECK.md
│
├─ Rédiger un rapport ou une communication
│    ├─ Rapport d'avancement (Status Report)
│    │    └─ contexts/STATUS_REPORT_CONTEXT.md
│    └─ Restitution Direction / Comex
│         └─ contexts/STAKEHOLDER_REPORT_CONTEXT.md
│
├─ Structurer les incidents et maîtriser les risques
│    ├─ Registre des incidents & risques
│    │    └─ contexts/ISSUE_RISK_CONTEXT.md
│    └─ Revue multi-projets transversale
│         └─ contexts/PMO_REVIEW_CONTEXT.md
│
├─ Gérer la relation et la communication Client
│    ├─ Notes d'explication et demandes d'arbitrage
│    │    └─ contexts/CLIENT_COMMUNICATION_CONTEXT.md
│    ├─ Demandes d'évolution de périmètre (Scope Change)
│    │    └─ contexts/SCOPE_CHANGE_CONTEXT.md
│    └─ Gestion de crise (Premières 72 heures)
│         └─ contexts/FIRE_RESPONSE_FIRST_72H.md
│
├─ Structurer les réunions et capitaliser le REX
│    ├─ Comptes rendus & Plan d'actions (TODO)
│    │    └─ contexts/MEETING_MINUTES_CONTEXT.md
│    └─ Rétrospective & Post-mortem
│         └─ contexts/RETROSPECTIVE_CONTEXT.md
│
├─ Chiffrages, qualité et plans de rattrapage
│    ├─ Hypothèses de chiffrage & Incertitudes
│    │    └─ contexts/ESTIMATION_CONTEXT.md
│    ├─ Incidents qualité & Défauts
│    │    └─ contexts/QUALITY_ISSUE_CONTEXT.md
│    └─ Plan de rattrapage de retard
│         └─ contexts/DELAY_RECOVERY_CONTEXT.md
│
└─ Remontée d'alerte de l'équipe technique vers le PM
     └─ contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md
```

---

## Matrice de sélection par situation opérationnelle

| Situation / Problématique | Contexte IA à mobiliser | Domaine de compétences associé |
|---|---|---|
| Vérifier si la santé globale du projet est compromise | `contexts/PROJECT_HEALTH_CHECK.md` | Diagnostic global de projet & Bilan de santé |
| Rédiger le rapport d'avancement hebdomadaire | `contexts/STATUS_REPORT_CONTEXT.md` | Pilotage de l'avancement & Reporting |
| Auditer l'exhaustivité du registre des incidents et des risques | `contexts/ISSUE_RISK_CONTEXT.md` | Gestion des incidents & Maîtrise des risques |
| Rédiger une note d'explication ou d'arbitrage pour le client | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` | Relation client & Négociation d'arbitrages |
| Gérer les premières 72h d'une crise opérationnelle majeure | `contexts/FIRE_RESPONSE_FIRST_72H.md` | Gestion de crise projet & Stabilisation |
| Transformer des notes de séance en compte rendu opérationnel | `contexts/MEETING_MINUTES_CONTEXT.md` | Animation de réunion & Relevé de décisions |
| Qualifier l'impact d'une demande de changement de spécifications | `contexts/SCOPE_CHANGE_CONTEXT.md` | Gestion du périmètre (Scope) & Change Management |
| Élaborer un plan de rattrapage suite à une dérive calendaire | `contexts/DELAY_RECOVERY_CONTEXT.md` | Pilotage du planning & Fast-tracking / Crashing |
| Instruire les causes et la remédiation d'un défaut qualité critique | `contexts/QUALITY_ISSUE_CONTEXT.md` | Assurance qualité, CAPA & Analyse causale |
| Structurer le bilan de fin de projet ou de sprint (REX) | `contexts/RETROSPECTIVE_CONTEXT.md` | Amélioration continue, KPT & Post-mortem |
| Préparer une note de synthèse exécutive pour la Direction | `contexts/STAKEHOLDER_REPORT_CONTEXT.md` | Gestion des parties prenantes & Reporting stratégique |
| Cadrer les hypothèses de chiffrage et les marges d'aléa | `contexts/ESTIMATION_CONTEXT.md` | Chiffrage d'effort & Maîtrise de l'incertitude |
| Piloter transversalement un portefeuille multi-projets PMO | `contexts/PMO_REVIEW_CONTEXT.md` | Pilotage PMO & Gouvernance de portefeuille |
| Remonter une alerte technique de l'équipe vers le chef de projet | `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md` | Communication technique-métier & Posture Lead Dev |

**Ressources complémentaires :**

- Pour évaluer votre profil et vos priorités d'apprentissage : [Diagnostic de formation](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- Pour accéder aux offres et réductions formateur : [Coupons de formation](https://techaide.jp/coupons/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- Pour consulter le catalogue complet des cursus : [Catalogue des formations](https://techaide.jp/courses/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)

---

## Modalités d'exploitation selon les outils d'IA

### 1. Utilisation dans une interface de chat standard

Quel que soit l'outil utilisé (ChatGPT, Claude, Gemini), appliquez la démarche suivante :

1. Coller le contenu de référence de `contexts/PM_CONTEXT.md` dans la conversation.
2. Coller le fichier `contexts/*.md` correspondant à votre cas d'usage.
3. Insérer les données de votre projet en veillant à les **anonymiser et les synthétiser**.
4. Formuler votre consigne en vous appuyant sur la section d'exemples du fichier de contexte.
5. Procéder systématiquement à la relecture et à la validation humaine du résultat.

### 2. Configuration permanente (ChatGPT Projects / Claude Projects / Gems)

Préconfigurer ces contextes dans les paramètres de vos projets ou assistants personnalisés évite les copier-coller répétitifs :

| Plateforme | Fichier d'instructions recommandé |
|---|---|
| ChatGPT | `instructions/chatgpt-project-instructions.md` |
| Gemini (Gems) | `instructions/gemini-instructions.md` |
| Claude Projects | `instructions/claude-project-instructions.md` |

Pour les guides d'installation pas à pas, consultez `docs/tools/chatgpt.md`, `docs/tools/gemini.md` et `docs/tools/claude.md`.

### 3. Combinaison avec les Skills Claude Code

Si vous utilisez Claude Code en environnement terminal, combinez les contextes avec les compétences du répertoire `.claude/skills/`.

Reportez-vous à la section suivante pour le détail des associations.

---

## Matrice de correspondance avec les Skills Claude Code

### Point d'entrée recommandé

| Objectif visé | Skill Claude Code associé |
|---|---|
| Diagnostiquer le besoin et choisir le bon contexte | `.claude/skills/pm-ai-diagnosis/SKILL.md` |

### Détection et anticipation des risques

| Objectif visé | Skill Claude Code associé |
|---|---|
| Détecter les signaux faibles et risques latents | `.claude/skills/project-risk-radar/SKILL.md` |
| Auditer les points de blocage et les risques | `.claude/skills/issue-risk-review/SKILL.md` |

### Prise de décision et arbitrage

| Objectif visé | Skill Claude Code associé |
|---|---|
| Structurer un arbitrage managérial complexe | `.claude/skills/pm-decision-support/SKILL.md` |

### Communication et restitution

| Objectif visé | Skill Claude Code associé |
|---|---|
| Adapter la stratégie de communication par acteur | `.claude/skills/stakeholder-strategy/SKILL.md` |
| Préparer une note ou un courriel client | `.claude/skills/client-communication/SKILL.md` |
| Structurer le rapport d'avancement périodique | `.claude/skills/status-report/SKILL.md` |

### Gouvernance et contrôle des livrables IA

| Objectif visé | Skill Claude Code associé |
|---|---|
| Auditer une sortie IA avant diffusion opérationnelle | `.claude/skills/ai-output-governance-review/SKILL.md` |

### Réunions, changements et gestion des dérives

| Objectif visé | Skill Claude Code associé |
|---|---|
| Rédiger le compte rendu et le relevé d'actions | `.claude/skills/meeting-minutes/SKILL.md` |
| Qualifier un changement de périmètre (Change Request) | `.claude/skills/scope-change-review/SKILL.md` |
| Bâtir un plan de rattrapage de retard | `.claude/skills/delay-recovery/SKILL.md` |
| Conduire les 72 premières heures d'une crise | `.claude/skills/fire-response-first-72h/SKILL.md` |

### Revues transversales et bilans de santé

| Objectif visé | Skill Claude Code associé |
|---|---|
| Revue globale 360° du projet sous l'angle PM | `.claude/skills/pm-review/SKILL.md` |
| Bilan de santé périodique (Health Check) | `.claude/skills/project-health-check/SKILL.md` |

> [!NOTE]
> Le répertoire `.claude/skills/` ne contient aucun script exécutable, hook, commande CLI, configuration MCP ou automatisation d'arrière-plan.
> Il s'agit exclusivement de documentation méthodologique guidant le raisonnement de Claude Code.

---

## Règles impératives de sécurité

> [!CAUTION]
> - Ne saisissez jamais de données d'affaires brutes non filtrées.
> - Masquez et anonymisez systématiquement : noms de clients, noms de personnes physiques, raisons sociales, clauses contractuelles et identifiants techniques.
> - Les livrables de l'IA ne remplacent en aucun cas l'arbitrage managérial ou légal.
> - Tout document destiné à un client, à la direction ou engageant les délais et coûts requiert impérativement une validation humaine préalable.

Pour plus de précisions, consultez [docs/ai-safety.md](ai-safety.md) ainsi que [docs/legal/DISCLAIMER.md](legal/DISCLAIMER.md).

---

## Parcours de montée en compétences

Pour approfondir les méthodes de gestion de projet et l'intégration avancée de l'IA dans votre pratique professionnelle, consultez le document [docs/learning-roadmap.md](learning-roadmap.md).

---

## Liens utiles

- [Découvrir la boîte à outils PM × IA](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit) (Vue d'ensemble)
- [Diagnostic d'orientation formation](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit) (Trouver la formation adaptée)
- [Laboratoire PM & IA](https://techaide.jp/community/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit) (Communauté et actualités)
