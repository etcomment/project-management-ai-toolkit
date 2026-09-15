# Journal des modifications / Changelog

Ce fichier répertorie l'historique des évolutions notables apportées au projet `project-management-ai-toolkit`.

## [Unreleased]

### Changements (Changed)

- Restructuration globale de l'arborescence du dépôt
  - Migration de `claude-code/skills/` vers `.claude/skills/`
  - Suppression des anciens répertoires par outil (`chatgpt/`, `gemini/`, `claude/`, `claude-code/`)
  - Centralisation des instructions de configuration système sous `instructions/`
  - Consolidation des guides méthodologiques par outil sous `docs/tools/`
  - Déplacement de `CONTRIBUTING.md` et `SECURITY.md` sous `.github/`
  - Déplacement de `DISCLAIMER.md` et `TERMS.md` sous `docs/legal/`
  - Déplacement de `CHANGELOG.md` et `ROADMAP.md` sous `docs/meta/`

### Ajouts (Added)

- Répertoire `instructions/` (directives de configuration pour ChatGPT, Gemini et Claude)
- Guides d'outillage : `docs/tools/chatgpt.md`, `docs/tools/gemini.md`, `docs/tools/claude.md`, `docs/tools/claude-code.md`

---

## [0.3.1] - 2026-05

### Ajouts (Added)

- Ajout de compétences (skills) Claude Code spécialisées par cas d'usage (désormais sous `.claude/skills/`) :
  - `.claude/skills/project-health-check/SKILL.md`
  - `.claude/skills/status-report/SKILL.md`
  - `.claude/skills/issue-risk-review/SKILL.md`
  - `.claude/skills/client-communication/SKILL.md`
  - `.claude/skills/fire-response-first-72h/SKILL.md`
  - `.claude/skills/meeting-minutes/SKILL.md`
  - `.claude/skills/scope-change-review/SKILL.md`
  - `.claude/skills/delay-recovery/SKILL.md`

### Changements (Changed)

- Intégration des modèles de requêtes directement dans chaque fichier de contexte (`contexts/*.md`), plaçant les contextes au cœur de l'architecture et supprimant le dossier `prompts/`.

---

## [0.3.0] - 2026-05

### Ajouts (Added)

- Ajout d'exemples d'application pratiques sur données fictives dans `examples/` :
  - `project-health-check-example.md`
  - `status-report-example.md`
  - `issue-risk-review-example.md`
  - `meeting-minutes-example.md`
  - `fire-response-first-72h-example.md`
  - `scope-change-example.md`
  - `delay-recovery-example.md`
  - `claude-code-pm-review-example.md`
- Ajout de guides de configuration et d'exemples pour ChatGPT et Gemini
- Ajout de contextes complémentaires couvrant de nouveaux cas d'usage :
  - `contexts/MEETING_MINUTES_CONTEXT.md`
  - `contexts/WEEKLY_MEETING_CONTEXT.md`
  - `contexts/SCOPE_CHANGE_CONTEXT.md`
  - `contexts/DELAY_RECOVERY_CONTEXT.md`
  - `contexts/QUALITY_ISSUE_CONTEXT.md`
  - `contexts/RETROSPECTIVE_CONTEXT.md`
  - `contexts/STAKEHOLDER_REPORT_CONTEXT.md`
  - `contexts/ESTIMATION_CONTEXT.md`
  - `contexts/PMO_REVIEW_CONTEXT.md`
  - `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md`

---

## [0.2.0] - 2026-05

### Ajouts (Added)

- Ajout de contextes additionnels : réunions, dérives de périmètre, retards, qualité, rétrospective, revues transversales PMO
- Ajout des premières compétences de revue PM pour Claude Code
- Ajout des guides d'utilisation par outil dans `docs/`

---

## [0.1.0] - 2026-05

### Ajouts (Added)

- Version initiale du README
- `DISCLAIMER.md`, `TERMS.md`, `SECURITY.md`, `LICENSE.md`
- Contextes fondamentaux sous `contexts/` :
  - `PM_CONTEXT.md`
  - `PROJECT_HEALTH_CHECK.md`
  - `STATUS_REPORT_CONTEXT.md`
  - `ISSUE_RISK_CONTEXT.md`
  - `FIRE_RESPONSE_FIRST_72H.md`
  - `CLIENT_COMMUNICATION_CONTEXT.md`
- Documentation initiale pour ChatGPT, Gemini, Claude et Claude Code
