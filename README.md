# Boîte à outils IA pour le management de projet (Project Management AI Toolkit)

Boîte à outils d'ingénierie de prompts et d'assistance IA conçue pour les Chefs de Projet (PM), Directeurs de Projet / PMO et Lead Développeurs. Elle regroupe des contextes opérationnels prêts à l'emploi (AI Contexts), des cas d'usage pratiques, des compétences pour Claude Code (Claude Code Skills) et des modèles de cadrage compatibles avec ChatGPT, Gemini, Claude et Claude Code.

## Pour débuter

Ce référentiel fournit aux professionnels du pilotage de projet des matrices de contexte (AI Contexts), des modèles d'instructions et des compétences spécialisées pour exploiter efficacement et en toute sécurité l'IA générative dans leurs missions quotidiennes.

Pour appréhender la vision d'ensemble du dispositif, vous pouvez consulter les ressources de la plateforme :

- [Découvrir la boîte à outils IA pour le pilotage de projet](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_top_ai_toolkit)
- [Diagnostiquer son profil et ses besoins d'apprentissage](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_top_course_diagnosis)
- [Accéder au Lab PM & IA](https://techaide.jp/community/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_top_community)
- [Consignes de sécurité et gouvernance des données](docs/ai-safety.md)

## Pour débuter : par où commencer ?

Si vous découvrez ce dépôt, suivez ce parcours recommandé pour une prise en main optimale :

1. Consultez [`docs/use-case-map.md`](docs/use-case-map.md) pour identifier les contextes IA adaptés à votre situation opérationnelle immédiate
2. Examinez les cas d'usage concrets dans [`examples/`](examples/)
3. Prenez impérativement connaissance du guide de sécurité [`docs/ai-safety.md`](docs/ai-safety.md) avant toute utilisation sur des projets réels
4. Explorez [`docs/learning-roadmap.md`](docs/learning-roadmap.md) pour approfondir vos compétences en pilotage de projet assisté par IA
5. Pour un apprentissage structuré, consultez le catalogue de formations sur le [site officiel de TechAide](https://techaide.jp/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_next_official_site)
6. En cas d'hésitation sur le cursus adapté, réalisez le [diagnostic d'orientation](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_next_course_diagnosis)
7. Pour suivre les évolutions et retours d'expérience, rejoignez le [Lab PM & IA](https://techaide.jp/community/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_next_community)

---

## Ce que vous apporte ce dépôt

- Structuration rigoureuse des hypothèses et données métier (AI Contexts) à transmettre à l'IA
- Fichiers de cadrage prêts à l'emploi : rapports d'avancement, revues des risques, communications clients, plans de crise
- Modèles d'illustration réalistes basés sur des jeux de données fictifs
- Grilles de contrôle et d'anonymisation préalable indispensables avant toute injection de données dans une IA

## Ce qui relève d'un apprentissage approfondi

Certaines compétences managériales fondamentales dépassent le cadre de simples modèles de prompts et exigent une maîtrise méthodique :

- Comprendre les fondements méthodologiques de chaque axe d'analyse
- Structurer sa démarche de réflexion managériale et son séquençage
- Adapter sa communication diplomatique et stratégique selon les parties prenantes (clients, direction, équipes)
- Auditer d'un œil critique les sorties de l'IA pour les transformer en arbitrages managériaux
- Déployer et standardiser l'usage de l'IA à l'échelle d'une organisation ou d'un PMO

Ces approfondissements et parcours de spécialisation sont détaillés sur le site officiel de TechAide.

---

## Structure du référentiel

Ce référentiel s'articule autour de plusieurs composants complémentaires :

```text
contexts/       → Fichiers de contexte IA : hypothèses de pilotage, critères d'arbitrage et modèles de prompts
instructions/   → Instructions système : directives de cadrage à copier dans ChatGPT / Gemini / Claude
docs/tools/     → Guides par outil : modes d'emploi spécifiques pour chaque plateforme d'IA
examples/       → Cas d'usage pratiques : simulations concrètes sur données fictives
.claude/skills/ → Compétences Claude Code : définitions de compétences pour l'audit et la revue PM
.github/        → Modèles et règles de gouvernance du dépôt
```

## Démarrage rapide (Quick Start)

### 1. Consulter le socle commun `contexts/PM_CONTEXT.md`

Ce fichier pose les principes universels et les exigences de rigueur applicables à toute tâche de gestion de projet assistée par IA.

### 2. Sélectionner le contexte adapté à votre cas d'usage

| Objectif opérationnel | Fichier de contexte |
|---|---|
| Réaliser un audit de santé de projet | `contexts/PROJECT_HEALTH_CHECK.md` |
| Rédiger un rapport d'avancement (Flash report) | `contexts/STATUS_REPORT_CONTEXT.md` |
| Auditer les problèmes et cartographier les risques | `contexts/ISSUE_RISK_CONTEXT.md` |
| Préparer une communication client délicate | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| Cadrer les premières 72h d'une situation de crise | `contexts/FIRE_RESPONSE_FIRST_72H.md` |

### 3. Soumettre l'instruction à votre assistant IA

```
En te basant sur le contexte de gestion de projet ci-dessous, analyse la situation opérationnelle avec la posture d'un chef de projet senior.

【Contenu du fichier de contexte sélectionné】

【Données de situation du projet (strictement anonymisées et débarrassées de toute mention confidentielle)】
```

### 4. Valider et arbitrer humainement la restitution

Les livrables générés par l'IA ne doivent en aucun cas être transmis sans relecture préalable à un client, une direction ou un tiers contractuel.

## Cas d'usage complémentaires

| Cas d'usage | Fichier de contexte |
|---|---|
| Structurer un compte rendu de réunion et plan d'actions (TODO) | `contexts/MEETING_MINUTES_CONTEXT.md` |
| Bâtir l'ordre du jour d'un comité d'avancement hebdomadaire | `contexts/WEEKLY_MEETING_CONTEXT.md` |
| Cadrer et arbitrer une modification de périmètre (Scope Change) | `contexts/SCOPE_CHANGE_CONTEXT.md` |
| Élaborer un plan de rattrapage en cas de dérive calendaire | `contexts/DELAY_RECOVERY_CONTEXT.md` |
| Analyser les causes racines d'un incident qualité et plan d'action | `contexts/QUALITY_ISSUE_CONTEXT.md` |
| Conduire une rétrospective ou un post-mortem de projet | `contexts/RETROSPECTIVE_CONTEXT.md` |
| Préparer un reporting stratégique pour les comités de gouvernance | `contexts/STAKEHOLDER_REPORT_CONTEXT.md` |
| Formaliser les hypothèses d'estimation et marges d'incertitude | `contexts/ESTIMATION_CONTEXT.md` |
| Réaliser une revue de portefeuille transversale sous l'angle PMO | `contexts/PMO_REVIEW_CONTEXT.md` |
| Structurer l'escalade d'un Lead Développeur vers le Chef de Projet | `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md` |

## Guides d'utilisation par plateforme

Pour exploiter ces contextes dans votre outil de prédilection, référez-vous aux guides dédiés dans `docs/tools/` :

| Outil d'IA | Guide dédié |
|---|---|
| ChatGPT | `docs/tools/chatgpt.md` |
| Gemini | `docs/tools/gemini.md` |
| Claude | `docs/tools/claude.md` |
| Claude Code | `docs/tools/claude-code.md` |

Les instructions système prêtes à être intégrées dans les réglages personnalisés de chaque outil figurent dans le dossier `instructions/`.

## Compétences Claude Code (Claude Code Skills)

Les compétences destinées à Claude Code sont regroupées dans le répertoire `.claude/skills/`.

Pour débuter ou vous orienter vers la compétence la plus adaptée, explorez en priorité :

- `.claude/skills/pm-ai-diagnosis/SKILL.md`
  - Diagnostic des problématiques PM et orientation vers les contextes et compétences appropriés
- `.claude/skills/project-risk-radar/SKILL.md`
  - Détection des signaux faibles et risques latents
- `.claude/skills/pm-decision-support/SKILL.md`
  - Structuration et formalisation des arbitrages managériaux
- `.claude/skills/stakeholder-strategy/SKILL.md`
  - Stratégie de communication différenciée par type d'interlocuteur
- `.claude/skills/ai-output-governance-review/SKILL.md`
  - Revue critique et sécurisation des livrables IA avant émission formelle

Pour l'ensemble des compétences disponibles (notamment `.claude/skills/pm-review/SKILL.md`, `project-health-check`, `status-report`, `issue-risk-review`), consultez `.claude/skills/README.md`.

Ces compétences sont des guides documentaires exclusifs de tout hook exécutable, commande d'automatisation ou configuration MCP.

Pour des exemples concrets de mise en œuvre, référez-vous à :

- `examples/pm-ai-diagnosis-example.md`
- `examples/project-risk-radar-example.md`
- `examples/ai-output-governance-review-example.md`

Pour les utilisateurs de Claude, exploitez les variantes balisées XML intégrées dans chaque fichier de contexte (`<task>`, `<input>`, `<constraints>`, `<output_format>`).

## Arborescence du dépôt

```
project-management-ai-toolkit/
├── README.md
├── LICENSE.md
├── .gitignore
│
├── contexts/           ← Fichiers de contexte IA : hypothèses PM et modèles de prompts
├── instructions/       ← Instructions système pour chaque plateforme d'IA
├── examples/           ← Cas d'usage pratiques sur données fictives
│
├── docs/
│   ├── usage-guide.md
│   ├── ai-safety.md
│   ├── use-case-map.md
│   ├── learning-roadmap.md
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
│       └── Autres compétences métiers (Skills)
│
└── .github/
    ├── CONTRIBUTING.md
    ├── SECURITY.md
    ├── pull_request_template.md
    └── ISSUE_TEMPLATE/
```

## Avertissements et responsabilités

> [!CAUTION]
> Ce référentiel fournit des guides méthodologiques et des modèles destinés à appuyer l'exercice du management de projet à l'aide de l'IA générative.
>
> Les restitutions de l'IA ne remplacent en aucun cas l'expertise professionnelle, l'arbitrage managérial, l'analyse juridique, fiscale, sociale, contractuelle ou sécuritaire.
>
> Toute utilisation en contexte opérationnel réel exige impérativement une relecture critique et une validation par un chef de projet qualifié.

## Données proscrites en entrée de l'IA

N'introduisez en aucun cas les données suivantes dans un outil d'IA :

- Données confidentielles contenant des noms de clients, d'entreprises ou de personnes réelles
- Données à caractère personnel, clauses contractuelles complètes ou comptes rendus intégraux de réunions
- Informations stratégiques non publiques ou code source propriétaire
- Clés d'API, mots de passe, jetons d'accès ou identifiants de sécurité
- Données dont la diffusion externe est prohibée par un accord de confidentialité (NDA) ou un contrat commercial

Préalablement à tout traitement, procédez systématiquement à une anonymisation rigoureuse et vérifiez la conformité avec la politique de sécurité des systèmes d'information (PSSI) de votre organisation.

## Précautions relatives à Claude Code

Les compétences situées sous `.claude/skills/` sont des référentiels méthodologiques.

Ce dépôt n'intègre délibérément aucun des éléments suivants :

- Hooks exécutables ou commandes système automatisées
- Configurations de serveurs MCP ou workflows GitHub Actions
- Exemples nécessitant des clés d'API réelles, des mécanismes d'auto-commit ou de déploiement automatique

## Exemples pratiques (Examples)

L'intégralité des scénarios proposés dans le répertoire `examples/` s'appuie sur des données purement fictives. Aucune information issue d'un projet réel n'y figure.

## Communauté et échanges

Le Lab PM & IA partage les retours d'expérience, les évolutions de ce référentiel, des conseils d'ingénierie de prompt et des parcours de formation continue.

Ces espaces d'échanges s'adressent aux professionnels souhaitant :

- Suivre les mises à jour des contextes et compétences IA
- Découvrir des modes d'utilisation avancés sur ChatGPT, Gemini, Claude et Claude Code
- Approfondir les thématiques clés du management de projet assisté par IA
- Accéder aux articles d'analyse et modules de spécialisation
- Bénéficier de retours d'expérience méthodologiques

Avant toute participation, merci de prendre connaissance des règles de courtoisie et de confidentialité de la communauté.

[Accéder au Lab PM & IA](https://techaide.jp/community/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_discord_community)

Pour plus de précisions, consultez [docs/community.md](docs/community.md).

> [!IMPORTANT]
> Les échanges individuels sur des projets réels, les données confidentielles et le support technique lié à des environnements privés ne sont pas pris en charge.
>
> Veillez à ne jamais publier de noms de clients, d'entreprises ou d'informations sensibles dans les espaces communautaires.

---

## Ressources associées

Ce référentiel est édité et maintenu par TechAide Inc. (TechAide Co., Ltd.).

- [Site officiel](https://techaide.jp/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_official_site)
- [Présentation de la boîte à outils IA PM](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_ai_toolkit)
- [Lab PM & IA](https://techaide.jp/community/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_community)
- [Diagnostic d'orientation de formation](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_course_diagnosis)
- [Codes promotionnels formateur](https://techaide.jp/coupons/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_coupons)
- [Catalogue des formations](https://techaide.jp/courses/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_courses)
- [Feuilles de route d'apprentissage](https://techaide.jp/learning-roadmaps/?utm_source=github&utm_medium=repository&utm_campaign=ai_toolkit&utm_content=readme_related_learning_roadmaps)

## Clause de non-responsabilité (Disclaimer)

Concernant les contenus du présent référentiel et les résultats générés par les outils d'IA à partir de celui-ci, TechAide Inc. ne fournit aucune garantie expresse ou tacite quant à leur exactitude, exhaustivité, utilité, actualité ou adéquation à un objectif particulier.

Pour plus de détails, consultez [`docs/legal/DISCLAIMER.md`](docs/legal/DISCLAIMER.md).

## Conditions d'utilisation (License)

Les conditions d'utilisation applicables à ce référentiel sont détaillées dans `LICENSE.md` et [`docs/legal/TERMS.md`](docs/legal/TERMS.md).

## Sécurité (Security)

Pour tout signalement ou préoccupation relative à la sécurité, référez-vous à [`.github/SECURITY.md`](.github/SECURITY.md).

## Contributions (Contributing)

Les signalements d'anomalies, de coquilles ou les propositions d'amélioration sont à soumettre via les Issues. Pour plus d'informations, consultez [`.github/CONTRIBUTING.md`](.github/CONTRIBUTING.md).

N'incluez jamais d'informations clients réelles, de données personnelles, de clauses contractuelles, de clés d'API ou de mots de passe dans les Issues ou Pull Requests.
