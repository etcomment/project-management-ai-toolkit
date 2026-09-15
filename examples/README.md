# Exemples — Cas d'usage pratiques (Examples)

Ce répertoire rassemble des cas d'usage illustrant concrètement l'exploitation des fichiers de `contexts/`.

---

## Objectif de ce répertoire

Ces exemples permettent de comprendre précisément comment exploiter chaque fichier de contexte à travers des jeux de données d'entrée réalistes, des modèles de prompts associés et les livrables attendus de l'IA.

---

## Consignes de sécurité et avertissements

> [!IMPORTANT]
> **Tous les exemples reposent sur des données fictives.** Aucun nom de client, d'entreprise, d'individu, de projet réel ni aucun identifiant de sécurité n'y figure.
>
> N'introduisez jamais d'informations réelles sensibles (noms de clients ou de projets, données personnelles, identifiants d'accès, données contractuelles) dans un service d'IA.
> Procédez systématiquement à une anonymisation ou une abstraction préalable. Pour plus de détails, consultez [docs/ai-safety.md](../docs/ai-safety.md).

> [!WARNING]
> **Les livrables générés par l'IA ne remplacent en aucun cas l'arbitrage managérial.** Tout contenu produit doit impérativement faire l'objet d'une relecture et d'une validation par un chef de projet humain.
> Avant toute transmission à un client, diffusion interne, négociation contractuelle, engagement sur les délais ou arbitrage budgétaire, le responsable de mission doit valider personnellement le contenu.

---

## Liste des cas pratiques

| Fichier d'exemple | Objet |
|---|---|
| [project-health-check-example.md](project-health-check-example.md) | Diagnostic d'état de santé d'un projet |
| [status-report-example.md](status-report-example.md) | Élaboration d'un rapport d'avancement (Flash report) |
| [issue-risk-review-example.md](issue-risk-review-example.md) | Revue des problèmes et analyse des risques |
| [meeting-minutes-example.md](meeting-minutes-example.md) | Transformation de notes brutes de réunion en compte rendu et plan d'actions (TODO) |
| [fire-response-first-72h-example.md](fire-response-first-72h-example.md) | Gestion de crise : cadrage des 72 premières heures |
| [scope-change-example.md](scope-change-example.md) | Gestion et arbitrage d'une modification de périmètre (Scope Change) |
| [delay-recovery-example.md](delay-recovery-example.md) | Élaboration d'un plan de rattrapage en cas de retard |
| [claude-code-pm-review-example.md](claude-code-pm-review-example.md) | Utilisation de la compétence de revue PM dans Claude Code |
| [pm-ai-diagnosis-example.md](pm-ai-diagnosis-example.md) | Diagnostic des enjeux PM / adoption de l'IA et sélection des contextes / compétences adaptés |
| [project-risk-radar-example.md](project-risk-radar-example.md) | Détection des signaux faibles et risques latents à partir des notes d'avancement |
| [ai-output-governance-review-example.md](ai-output-governance-review-example.md) | Revue de gouvernance d'un livrable IA avant transmission au client |

---

## Matrice de correspondance des fichiers utilisés

| Exemple | Fichiers de contexte et compétences associés |
|---|---|
| project-health-check-example.md | `contexts/PM_CONTEXT.md`, `contexts/PROJECT_HEALTH_CHECK.md` |
| status-report-example.md | `contexts/PM_CONTEXT.md`, `contexts/STATUS_REPORT_CONTEXT.md` |
| issue-risk-review-example.md | `contexts/PM_CONTEXT.md`, `contexts/ISSUE_RISK_CONTEXT.md` |
| meeting-minutes-example.md | `contexts/PM_CONTEXT.md`, `contexts/MEETING_MINUTES_CONTEXT.md` |
| fire-response-first-72h-example.md | `contexts/PM_CONTEXT.md`, `contexts/FIRE_RESPONSE_FIRST_72H.md` |
| scope-change-example.md | `contexts/PM_CONTEXT.md`, `contexts/SCOPE_CHANGE_CONTEXT.md` |
| delay-recovery-example.md | `contexts/PM_CONTEXT.md`, `contexts/DELAY_RECOVERY_CONTEXT.md` |
| claude-code-pm-review-example.md | `contexts/PM_CONTEXT.md`, `.claude/skills/pm-review/SKILL.md` |
| pm-ai-diagnosis-example.md | `.claude/skills/pm-ai-diagnosis/SKILL.md`, `contexts/PM_CONTEXT.md`, `contexts/PROJECT_HEALTH_CHECK.md`, `contexts/STATUS_REPORT_CONTEXT.md`, `contexts/ISSUE_RISK_CONTEXT.md`, `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| project-risk-radar-example.md | `.claude/skills/project-risk-radar/SKILL.md`, `contexts/PROJECT_HEALTH_CHECK.md`, `contexts/ISSUE_RISK_CONTEXT.md`, `contexts/DELAY_RECOVERY_CONTEXT.md` |
| ai-output-governance-review-example.md | `.claude/skills/ai-output-governance-review/SKILL.md`, `contexts/CLIENT_COMMUNICATION_CONTEXT.md`, `contexts/STATUS_REPORT_CONTEXT.md`, `docs/ai-safety.md` |

---

## Contrôle humain préalable à toute utilisation opérationnelle

Dans chaque exemple, la section « Human Review Points » recense les axes d'analyse critiques que le chef de projet doit obligatoirement contrôler sur le livrable produit par l'IA.

N'utilisez jamais les sorties brutes de l'IA pour une présentation client, une communication de direction ou une formalisation contractuelle. La décision finale et la responsabilité incombent toujours à l'humain.

Pour plus de précisions, reportez-vous à [docs/usage-guide.md](../docs/usage-guide.md) et [docs/legal/DISCLAIMER.md](../docs/legal/DISCLAIMER.md).

---

## Ce que ces exemples vous apprennent

- Comment structurer les hypothèses et données de cadrage (AI Contexts) à transmettre à l'IA
- Quels points de contrôle spécifiques le chef de projet doit examiner
- Ce qui peut être délégué à l'IA et ce qui requiert un arbitrage humain
- Les grilles d'analyse avant tout partage avec les clients, la direction ou l'équipe

---

## Ressources complémentaires recommandées

- Choisir un outil selon votre besoin : [`docs/use-case-map.md`](../docs/use-case-map.md)
- Suivre la progression d'apprentissage : [`docs/learning-roadmap.md`](../docs/learning-roadmap.md)
- Bonnes pratiques de sécurité : [`docs/ai-safety.md`](../docs/ai-safety.md)
- Répertoire des compétences Claude Code : [`../.claude/skills/README.md`](../.claude/skills/README.md)
