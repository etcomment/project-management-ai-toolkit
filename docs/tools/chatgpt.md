# Guide d'utilisation de ChatGPT / ChatGPT Usage Guide

Guide pratique pour exploiter le présent référentiel avec OpenAI ChatGPT.

> [!IMPORTANT]
> Ne saisissez jamais de données clients réelles, informations personnelles, clauses contractuelles ou identifiants techniques (clés d'API, mots de passe) dans ChatGPT.
> Les sorties de l'IA ne remplacent pas l'arbitrage managérial. Tout livrable doit impérativement être relu, vérifié et ajusté par un humain.

---

## `contexts/` — Composant central (AI Contexts)

Le cœur méthodologique réside dans le répertoire `contexts/`. Chaque fichier rassemble les prérequis métier, les critères d'arbitrage et les modèles d'invites (Prompt Templates).

Les gabarits d'instructions pour les paramètres système se trouvent sous `instructions/`.

---

## Fichiers de configuration système à utiliser

| Fichier | Emplacement de configuration |
|---|---|
| `instructions/chatgpt-project-instructions.md` | Champ Instructions des Projets ChatGPT (ChatGPT Projects) |
| `instructions/custom-gpt-instructions.md` | Champ Instructions de vos Custom GPTs |

Ces fichiers sont des directives système prêtes à l'emploi destinées aux paramètres de configuration de l'outil.

---

## Modes d'exploitation

### Option 1 : Utilisation dans une conversation standard

1. Copier le contenu de `contexts/PM_CONTEXT.md`.
2. Le coller en préambule d'une nouvelle conversation.
3. Coller le fichier de contexte adapté à votre besoin (`contexts/*.md`) puis renseigner les informations anonymisées de votre projet.
4. Procéder à la validation humaine du résultat produit.

```text
Vous agirez en vous conformant strictement au contexte méthodologique ci-dessous :

[Coller ici le contenu de PM_CONTEXT.md]

---

[Coller ici le contenu du fichier de contexte thématique]

---

[Renseigner ici les données de votre projet (strictement anonymisées)]
```

### Option 2 : Configuration dans ChatGPT Projects

1. Créer un nouveau projet dans ChatGPT.
2. Coller le contenu de `instructions/chatgpt-project-instructions.md` dans le champ « Instructions » du projet.
3. Dans les conversations du projet, transmettez directement les informations anonymisées accompagnées du contexte spécifique sans avoir à réinjecter les consignes de base.

### Option 3 : Création d'un Custom GPT dédié

1. Coller le contenu de `instructions/custom-gpt-instructions.md` dans le champ « Instructions » du configurateur de GPT.
2. Téléverser les fichiers de référence comme `contexts/PM_CONTEXT.md` dans la section « Knowledge ».
3. Formuler vos requêtes avec vos données projets anonymisées.

---

## Schéma récapitulatif du flux de travail

```text
Exploitation avec ChatGPT
│
├─ Conversation standard
│    └─ Coller contexts/*.md directement dans le fil de discussion
│
├─ ChatGPT Projects
│    └─ Paramétrer instructions/chatgpt-project-instructions.md
│
└─ Custom GPT
     └─ Paramétrer instructions/custom-gpt-instructions.md

Démarche méthodologique commune :
PM_CONTEXT.md → Fichier thématique contexts/*.md → Données anonymisées → Validation humaine
```

---

## Sélection des contextes thématiques par cas d'usage

| Cas d'usage | Fichier de contexte associé |
|---|---|
| Bilan de santé global du projet | `contexts/PROJECT_HEALTH_CHECK.md` |
| Rapport d'avancement périodique | `contexts/STATUS_REPORT_CONTEXT.md` |
| Registre des incidents et risques | `contexts/ISSUE_RISK_CONTEXT.md` |
| Communication et argumentaire client | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| Gestion de crise (Premières 72h) | `contexts/FIRE_RESPONSE_FIRST_72H.md` |
| Compte rendu de réunion & Relevé de décisions | `contexts/MEETING_MINUTES_CONTEXT.md` |

Pour une orientation détaillée, consultez [docs/use-case-map.md](../use-case-map.md).

---

## Exemples d'anonymisation avant saisie

| Donnée réelle (À proscrire) | Formulation anonymisée conforme |
|---|---|
| Société Alpha Solutions (Client) | Client A |
| Jean Dupont (Chef de projet client) | Intervenant A / Responsable Client |
| api_key_xxxxxxxxxx | [SUPPRIMÉ] |
| Montant contractuel : 350 000 € | Budget : Ordre de grandeur de quelques centaines de k€ |
| Projet Refonte ERP 2026 | Projet X |

---

## Cas pratique illustratif (Données fictives)

Exemple d'application concrète sur des données simulées :

### Scénario : Bilan de santé projet (Health Check)

**Ressources mobilisées**
- `contexts/PM_CONTEXT.md`
- `contexts/PROJECT_HEALTH_CHECK.md`

**Données d'entrée anonymisées (Données fictives)**

```
【Synthèse du projet】
- Typologie : Développement d'un système métier sur mesure (au forfait)
- Phase : Tests d'intégration / Recette technique
- Avancement global : 65%

【Situation constatée】
- Les spécifications de l'API externe n'étant pas stabilisées, 3 fonctionnalités restent bloquées
- Taux de couverture de test à seulement 40% (retard sur la campagne de recette)
- Le client a formulé 2 demandes d'évolution majeures non encore arbitrées
```

**Modèle de requête (Prompt)**

```
Sur la base des contextes de référence ci-dessous, réalisez un bilan de santé (Health Check) de notre situation selon une perspective Chef de Projet :

[Contenu de PM_CONTEXT.md]
[Contenu de PROJECT_HEALTH_CHECK.md]

【Situation du projet (Données anonymisées)】
(Coller ici les données d'entrée ci-dessus)
```

**Points de contrôle humain (Human Review)**
- Vérifier la pertinence du niveau de criticité attribué au regard de la réalité terrain.
- Réajuster la priorité opérationnelle des actions proposées.
- Ne jamais diffuser la synthèse brute générée sans validation managériale préalable.

---

## Checklist de validation des résultats

- [ ] L'analyse concorde fidèlement avec les événements réels du projet
- [ ] Le ton et le registre d'expression sont adaptés aux relations internes et clients
- [ ] Les formulations relatives au périmètre contractuel, aux délais et aux coûts sont exemptes d'engagements imprudents
- [ ] Le livrable a été validé par un responsable humain habilité avant transmission

---

## Documents associés

- [docs/ai-safety.md](../ai-safety.md) — Règles de sécurité et données autorisées
- [docs/legal/DISCLAIMER.md](../legal/DISCLAIMER.md) — Clause de non-responsabilité

---

## Liens utiles

- [Découvrir la boîte à outils PM × IA](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [Laboratoire PM & IA](https://techaide.jp/community/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [Diagnostic d'orientation formation](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
