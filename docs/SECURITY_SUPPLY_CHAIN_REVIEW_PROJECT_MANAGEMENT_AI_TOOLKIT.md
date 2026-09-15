# Rapport d'audit de sécurité et de la chaîne d'approvisionnement logicielle

## Informations d'audit

| Rubrique | Données d'audit |
|---|---|
| Date de l'audit | 13 mai 2026 |
| Dépôt audité | techaide-jp/project-management-ai-toolkit |
| Auditeur | GitHub Copilot (Claude Sonnet 4.6) / Perspective Ingénieur Cybersécurité |
| Type d'audit | Analyse statique (lecture des fichiers, recherche de motifs de vulnérabilité) |
| Opérations destructrices exécutées | Aucune |

---

## 1. Vue d'ensemble de la structure du dépôt

### Classification typologique

**Dépôt documentaire et modèles de distribution publique**

Aucun fichier exécutable (scripts shell, JavaScript, TypeScript, Python, PowerShell, etc.) n'est présent dans le référentiel.
L'intégralité du contenu est constituée de fichiers Markdown (`.md`), formant une boîte à outils méthodologique dédiée à la gestion de projet (PM) : contextes IA, exemples pratiques, compétences Claude Code et canevas professionnels.

### Arborescence du dépôt (Périmètre public)

```
project-management-ai-toolkit/
├── README.md
├── LICENSE.md
├── .gitignore
├── contexts/           Contextes méthodologiques d'IA pour PM (16 fichiers)
├── instructions/       Instructions de configuration système pour les outils IA (4 fichiers)
├── examples/           Exemples d'application sur données fictives (9 fichiers)
├── docs/               Guides d'utilisation, sécurité IA, mentions légales (8 fichiers)
│   ├── tools/          Guides par outil IA
│   ├── legal/          DISCLAIMER.md / TERMS.md
│   └── meta/           CHANGELOG.md / ROADMAP.md
├── .claude/skills/     Compétences Claude Code PM (9 fichiers)
└── .github/            SECURITY.md / CONTRIBUTING.md / ISSUE_TEMPLATE / PR Template
```

### Éléments absents (Contrôlés et confirmés)

| Élément | Statut |
|---|---|
| package.json | Absent |
| node_modules/ | Absent |
| .github/workflows/*.yml | Absent |
| .github/dependabot.yml | Absent |
| .vscode/tasks.json | Absent |
| .vscode/settings.json | Absent |
| .vscode/launch.json | Absent |
| .claude/settings.json | Absent |
| .claude/settings.local.json | Absent |
| CLAUDE.md | Absent |
| scripts/ | Absent |
| bin/ | Absent |
| tools/ | Absent (`docs/tools/` existe mais contient uniquement du Markdown) |
| Dockerfile | Absent |
| docker-compose.yml | Absent |
| *.sh / *.ps1 / *.py / *.js / *.ts | Absent |

---

## 2. Inventaire des fichiers examinés

```
Nombre total de fichiers audités : 54 fichiers (exclusivement .md ou .yml)
.gitignore (fichier de configuration texte)
.github/ISSUE_TEMPLATE/config.yml
```

---

## 3. Évaluation des risques en distribution publique

### Synthèse

Le dépôt est conçu de manière native comme un **référentiel exclusivement documentaire**, excluant délibérément tout code binaire, script ou fichier de configuration automatisée.

Les documents `README.md`, `SECURITY.md`, `ai-safety.md` et `docs/tools/claude-code.md` intègrent des avertissements de sécurité multicouches à destination des utilisateurs. La posture de sécurité pour une diffusion publique est exemplaire et conforme aux standards de l'art.

### Mesures de sécurité formellement vérifiées

| Règle de sécurité | Statut |
|---|---|
| Absence explicite de hooks (README / SECURITY.md / Ensemble des Skills) | ✅ Conforme |
| Absence explicite de commandes d'exécution automatique | ✅ Conforme |
| Absence explicite de configurations MCP et de workflows GitHub Actions | ✅ Conforme |
| Interdiction formelle de saisie de clés d'API et d'identifiants (README / SECURITY.md / ai-safety.md) | ✅ Conforme |
| Utilisation exclusive de données fictives et anonymisées dans les exemples | ✅ Conforme |
| Mention obligatoire de la relecture et validation humaine des sorties IA | ✅ Conforme |
| Checklist de sécurité intégrée dans les modèles d'Issues et de Pull Requests | ✅ Conforme |
| Point de contrôle « Aucun ajout de hook, script shell ou action GitHub » dans le template de PR | ✅ Conforme |
| Charte de sécurité claire dans CONTRIBUTING.md | ✅ Conforme |
| Inventaire exhaustif des données proscrites dans docs/ai-safety.md | ✅ Conforme |

---

## 4. Audit des fichiers associés à Claude Code

### Périmètre examiné

- `.claude/settings.json` — **Inexistant** (délibérément non distribué)
- `.claude/settings.local.json` — **Inexistant** (délibérément non distribué)
- `.claude/commands/` — **Inexistant**
- `.claude/agents/` — **Inexistant**
- `.claude/skills/` — **9 fichiers identifiés** (tous au format `.md`)
- `CLAUDE.md` — **Inexistant**

### Audit des fichiers Skill

| Skill | Définition de hooks | Flux réseau externe | Référence à des tokens | Commandes système | Clause de non-exécution |
|---|---|---|---|---|---|
| pm-review/SKILL.md | Aucun | Aucun | Aucune | Aucune | ✅ Présente |
| status-report/SKILL.md | Aucun | Aucun | Aucune | Aucune | ✅ Présente |
| project-health-check/SKILL.md | Aucun | Aucun | Aucune | Aucune | ✅ Présente |
| issue-risk-review/SKILL.md | Aucun | Aucun | Aucune | Aucune | ✅ Présente |
| client-communication/SKILL.md | Aucun | Aucun | Aucune | Aucune | ✅ Présente |
| fire-response-first-72h/SKILL.md | Aucun | Aucun | Aucune | Aucune | ✅ Présente |
| meeting-minutes/SKILL.md | Aucun | Aucun | Aucune | Aucune | ✅ Présente |
| scope-change-review/SKILL.md | Aucun | Aucun | Aucune | Aucune | ✅ Présente |
| delay-recovery/SKILL.md | Aucun | Aucun | Aucune | Aucune | ✅ Présente |

**Conclusion d'audit : Aucun risque détecté. Tous les fichiers de compétences sont de purs guides documentaires pour le pilotage PM.**

---

## 5. Audit des fichiers de configuration VS Code

- `.vscode/tasks.json` — **Inexistant**
- `.vscode/settings.json` — **Inexistant**
- `.vscode/launch.json` — **Inexistant**
- `.vscode/extensions.json` — **Inexistant**

**Conclusion d'audit : Aucun risque. Le répertoire `.vscode/` est absent et correctement exclu dans `.gitignore`.**

---

## 6. Audit des dépendances npm / Node.js

- `package.json` — **Inexistant**
- `package-lock.json` — **Inexistant** (exclu dans `.gitignore`)
- `pnpm-lock.yaml` — **Inexistant**
- `yarn.lock` — **Inexistant**
- `npm-shrinkwrap.json` — **Inexistant**
- `.npmrc` — **Inexistant**
- `node_modules/` — **Inexistant**

**Conclusion d'audit : Aucune dépendance d'exécution npm à ce jour.**

Aucune mention de `npm install`, `npx` ou `npm exec` ne figure dans la documentation (vérifié par recherche d'IoC).

---

## 7. Audit des composants GitHub Actions

- `.github/workflows/` — **Inexistant**
- `.github/dependabot.yml` — **Inexistant**

**Conclusion d'audit : L'absence de workflows élimine tout risque d'attaque sur la chaîne CI/CD.**

---

## 8. Audit des répertoires scripts, tools et bin

- `scripts/` — **Inexistant**
- `bin/` — **Inexistant**
- `tools/` — **Inexistant** (`docs/tools/` contient exclusivement du Markdown)

**Conclusion d'audit : Aucun script exécutable présent.**

---

## 9. Contrôle d'absence de secrets, données personnelles et informations internes

### Mots-clés contrôlés et résultats

| Mot-clé de recherche | Résultat de l'analyse |
|---|---|
| OPENAI_API_KEY / ANTHROPIC_API_KEY / GEMINI_API_KEY / GOOGLE_API_KEY | Aucune correspondance |
| GITHUB_TOKEN / GH_TOKEN / NPM_TOKEN / NODE_AUTH_TOKEN | Aucune correspondance |
| PRIVATE_KEY / SECRET_KEY / ACCESS_TOKEN / REFRESH_TOKEN | Aucune correspondance |
| CLIENT_SECRET / SERVICE_ACCOUNT | Aucune correspondance |
| .env / .ssh / known_hosts | Uniquement en règles d'exclusion dans `.gitignore` |
| credentials.json / token.json / service-account.json | Uniquement en règles d'exclusion dans `.gitignore` |
| C:\Users\ / /Users/ / /home/ | Métadonnées internes Git uniquement (non publiées) |
| Adresses e-mails réelles | Métadonnées internes Git uniquement (non publiées) |
| URLs internes sensibles | Aucune correspondance |
| Clés d'API au format sk- ou pk_ | Aucune correspondance |

### Précisions

Les métadonnées Git internes locales mentionnent l'e-mail du committer (`ryota.suzuki@techaide.jp`), ce qui est inhérent au protocole Git et ne constitue pas une fuite documentaire.
Les mentions du domaine `techaide.jp` dans le `README.md` et les mentions légales correspondent aux informations publiques officielles de l'éditeur.

**Conclusion d'audit : Aucun secret, identifiant technique ou donnée confidentielle n'est présent dans le référentiel.**

---

## 10. Audit des avertissements de sécurité dans la documentation

### Vérification des clauses impératives

| Clause de vigilance | Emplacement | Statut |
|---|---|---|
| Relecture et vérification humaine avant utilisation des fichiers | README.md / SECURITY.md | Présente |
| Mise en garde contre l'ajout inconsidéré de hooks dans .claude/settings.json | SECURITY.md §6 / claude-code.md | Intégrée |
| Alerte contre les tâches d'exécution automatique dans .vscode/tasks.json | SECURITY.md §6 | Intégrée |
| Proscription de commandes non fiables (npx, curl, wget) | SECURITY.md §6 | Intégrée |
| Interdiction absolue d'inclure des secrets ou clés API dans les invites | README.md / SECURITY.md / ai-safety.md | Présente |
| Vérification des politiques internes avant soumission de données d'entreprise | SECURITY.md / ai-safety.md | Présente |
| Revue préalable des contenus au regard de l'environnement métier de l'entreprise | README.md / ai-safety.md | Présente |
| Explication des risques liés aux tokens OIDC et actions/cache | SECURITY.md §6 | Intégrée |

---

## 11. Audit du fichier .gitignore

Toutes les règles indispensables pour neutraliser le risque de commit accidentel de secrets d'infrastructure (`token.json`, `service-account.json`, `client_secret.json`), de répertoires de compilation (`dist/`, `build/`) et de configurations locales (`.claude/settings.local.json`) sont dûment en place.

---

## 12. Surveillance continue et Dependabot

En l'absence de `package.json` et de workflows GitHub Actions, la configuration de Dependabot n'est pas requise à ce stade. Elle sera recommandée si des dépendances d'outillage ou des actions CI/CD sont introduites ultérieurement.

---

## 13. Synthèse des indicateurs de compromission (IoC) contrôlés

Plus de 30 motifs et signatures d'attaque sur la chaîne d'approvisionnement (malwares npm, scripts malveillants, injections de hooks) ont été passés en revue :
- Les occurrences des termes `hooks` et `shell` correspondent exclusivement aux clauses de mise en garde (« ne contient aucun hook »).
- Aucun motif suspect ou indicateur malveillant n'a été détecté dans les fichiers suivis par git.

---

## 14. Matrice des constatations d'audit

| Réf | Niveau de sévérité | Composant | Constat | Mesure corrective |
|---|---|---|---|---|
| R-01 | **FAIBLE (LOW)** | `.gitignore` | Manque d'exclusions pour certains formats de secrets et builds | **Corrigé** |
| R-02 | **FAIBLE (LOW)** | `.github/SECURITY.md` | Nécessité de formaliser les risques d'attaques 2026 sur la chaîne d'approvisionnement | **Corrigé** |
| R-03 | **INFO** | `.github/dependabot.yml` | Absent (non requis en l'absence de dépendances) | Prévu pour les évolutions futures |
| R-04 | **INFO** | `.github/workflows/` | Absent (aucun pipeline CI/CD actif) | Documenté à titre préventif dans SECURITY.md |

---

## 15. Plan de gouvernance et règles d'exploitation futures

### Règles impératives permanentes

1. Ne jamais introduire de fichier `.claude/settings.json` dans la distribution publique (principe d'exclusion des hooks).
2. Maintenir le répertoire `.claude/skills/` dans un format strictement documentaire Markdown, sans commandes exécutables.
3. Conserver exclusivement des données fictives dans les exemples (`examples/`).
4. Vérifier scrupuleusement la checklist de sécurité avant tout merge de Pull Request.
5. Conduire une analyse statique trimestrielle de recherche de secrets.

---

## Synthèse générale de l'audit de sécurité

- **Signe d'infection ou de compromission : AUCUN**
- **Risque critique pour la distribution publique : AUCUN**
- **Risque lié aux hooks Claude Code : NUL** (absence de tout fichier settings de hooks)
- **Risque lié aux tâches VS Code : NUL** (répertoire `.vscode/` inexistant)
- **Risque d'injection de dépendances npm : NUL** (absence de tout package.json)
- **Risque de compromission CI/CD GitHub Actions : NUL** (aucun workflow déployé)
- **Fuites de secrets ou données sensibles : AUCUNE**
- **Anomalies traitées et corrigées : 2 (Renforcement du `.gitignore` et enrichissement de `SECURITY.md`)**
- **Mesures préconisées : Maintien de la politique d'audit statique trimestriel.**
