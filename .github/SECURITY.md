# Politique de sécurité / Security Policy

---

## 1. Politique de sécurité de ce dépôt

Le présent dépôt « project-management-ai-toolkit » propose des contextes IA, des modèles de prompts (Prompt Templates), des compétences Claude Code (Claude Code Skills) et des cas d'usage réels adaptés aux missions de gestion de projet (PM).

Sa maintenance et son administration reposent sur les principes de sécurité décrits ci-après.

---

## 2. Éléments exclus par conception de ce dépôt

Ce dépôt n'intègre délibérément aucun des composants suivants :

- Hooks exécutables
- Scripts shell (.sh) ou scripts PowerShell (.ps1)
- Workflows GitHub Actions
- Fichiers de configuration de serveurs MCP
- Fichiers package.json ou définitions de workflows
- Clés d'API, jetons d'accès, mots de passe ou informations d'authentification
- Dispositifs de commit ou de déploiement automatisés
- Configurations établissant des flux réseau sortants automatisés vers des services tiers

Les modèles de compétences pour Claude Code (situés dans le répertoire `.claude/skills/`) sont des guides méthodologiques montrant comment structurer une revue PM assistée par IA, et ne fournissent aucune fonctionnalité d'exécution automatisée.

---

## 3. Règles applicables aux Issues et Pull Requests

Ne publiez en aucun cas les informations suivantes dans les Issues ou Pull Requests de ce dépôt :

- Données à caractère personnel (nom, prénom, adresse e-mail, numéro de téléphone, etc.)
- Informations clients ou dénominations sociales d'entreprises clientes
- Clés d'API, tokens d'accès, mots de passe ou secrets d'authentification
- Données contractuelles ou informations confidentielles d'affaires
- Informations internes d'entreprise non publiques

**En cas de publication accidentelle d'une donnée sensible dans un commentaire, ne complétez pas l'Issue publique et contactez immédiatement les administrateurs du dépôt.**

---

## 4. Signalement d'une vulnérabilité ou d'un incident de sécurité

Si vous décelez l'une des anomalies suivantes dans les fichiers du dépôt, n'ouvrez pas d'Issue publique et prévenez-nous par le canal mentionné ci-dessous :

- Présence suspectée d'une information confidentielle ou d'une donnée personnelle
- Présence d'instructions dangereuses ou d'un exemple présentant une vulnérabilité
- Tout autre motif d'inquiétude lié à la sécurité

**Point de contact :**

TechAide Inc. (TechAide Inc.)  
Site web : https://techaide.jp/contact/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit

*(Veuillez nous contacter via le formulaire de contact du site officiel. Ne mentionnez aucun détail confidentiel ou vulnérabilité dans une Issue ou un commentaire public.)*

---

## 5. Recommandations aux utilisateurs

Lorsque vous exploitez les contextes et prompts de ce référentiel au sein d'un service d'IA générative, appliquez scrupuleusement les consignes suivantes :

- N'y soumettez jamais d'informations clients, de données personnelles, de clauses contractuelles, d'identifiants, de clés d'API ou de mots de passe
- Vérifiez la conformité avec la politique de sécurité des systèmes d'information (PSSI) de votre organisation
- Vérifiez les clauses de confidentialité (NDA) et stipulations contractuelles conclues avec vos clients
- Examinez les conditions d'utilisation, la politique de confidentialité et la politique d'exploitation des données de la plateforme d'IA utilisée

Pour plus de précisions, reportez-vous au guide [docs/ai-safety.md](../docs/ai-safety.md).

---

## 6. Précautions relatives aux fichiers de configuration et scripts externes

Ce dépôt ne contient en lui-même aucun fichier exécutable, hook ou tâche planifiée automatique.  
Cependant, lors de l'importation ou de l'analyse de fichiers de configuration provenant de dépôts tiers (`.claude/settings.json`, `.vscode/tasks.json`, `package.json`, etc.), la plus grande vigilance s'impose (des vecteurs d'attaque sur la chaîne d'approvisionnement npm, le détournement des hooks Claude Code et l'automatisation VS Code tasks ayant été documentés en 2026).

### À propos des hooks dans `.claude/settings.json`

- Ce dépôt ne distribue aucun fichier `.claude/settings.json`. Il ne comporte aucun hook.
- **Si vous adoptez le `.claude/settings.json` d'un dépôt tiers, examinez impérativement la totalité de la section `hooks`.**
- Si les hooks `PreToolUse`, `PostToolUse` ou `SessionStart` invoquent curl, wget, powershell, npm, npx, bash ou python, analysez minutieusement la chaîne de traitement avant exécution.
- Le fichier `.claude/settings.local.json` est un fichier de préférences locales strictement personnel : ne le commitez jamais et ne le partagez pas.

### À propos de l'exécution automatique dans `.vscode/tasks.json`

- Ce dépôt ne distribue pas de fichier `.vscode/tasks.json`.
- **Si vous importez le `.vscode/tasks.json` d'un autre projet, inspectez scrupuleusement les tâches configurées avec `runOn: folderOpen` ou planifiées au démarrage.**
- N'ajoutez aucune tâche non éprouvée à votre espace de travail.

### À propos de l'exécution de scripts ou packages externes

- **Les commandes `npx <package>` ou `npm exec` non épinglées à une version stricte ou dépourvues de fichier de verrouillage (lockfile) peuvent exécuter du code malveillant à votre insu.**
- Proscrivez formellement l'exécution directe de scripts téléchargés à la volée via `curl URL | sh`, `wget URL | sh` ou `Invoke-WebRequest`.
- Examinez les scripts `postinstall`, `preinstall` et `prepare` avant d'exécuter `npm install` sur un `package.json` issu d'une source non vérifiée.

### À propos de GitHub Actions

- L'utilisation du déclencheur `pull_request_target` dans les workflows expose à des risques d'élévation de privilèges via du code issu de PR externes.
- Prenez garde aux risques d'empoisonnement de cache avec la directive `restore-keys` de l'action `actions/cache`.
- N'attribuez la permission `id-token: write` qu'aux jobs qui le requièrent strictement.

---

## 7. Documents associés

- Clause de non-responsabilité : [docs/legal/DISCLAIMER.md](../docs/legal/DISCLAIMER.md)
- Conditions d'utilisation : [docs/legal/TERMS.md](../docs/legal/TERMS.md)
- Guide de sécurité pour l'IA : [docs/ai-safety.md](../docs/ai-safety.md)

---

*TechAide Inc. (TechAide Co., Ltd.)*  
*https://techaide.jp/*
