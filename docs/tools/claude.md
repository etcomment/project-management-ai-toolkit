# Guide d'utilisation d'Anthropic Claude / Claude Usage Guide

Guide pratique pour exploiter le présent référentiel avec Claude et Claude Projects.

> [!IMPORTANT]
> Ne saisissez jamais de données clients réelles, informations personnelles, clauses contractuelles ou identifiants d'accès (clés d'API, mots de passe) dans Claude.
> Les livrables de l'IA ne remplacent pas l'arbitrage managérial. Tout contenu produit doit impérativement être relu, vérifié et ajusté par un responsable humain.

---

## `contexts/` — Composant central (AI Contexts)

Le cœur méthodologique réside dans le répertoire `contexts/`. Chaque fichier rassemble les prérequis métier, les critères d'arbitrage et les modèles d'invites (Prompt Templates).

Les gabarits d'instructions pour les paramètres système se trouvent sous `instructions/`.

---

## Fichiers de configuration système à utiliser

| Fichier | Emplacement de configuration |
|---|---|
| `instructions/claude-project-instructions.md` | Champ Project Instructions de Claude Projects |

Ce fichier fournit les directives prêtes à l'emploi à intégrer dans les paramètres d'instructions de projet de Claude.

---

## Modes d'exploitation

### Option 1 : Utilisation dans une conversation standard

1. Copier le contenu de `contexts/PM_CONTEXT.md`.
2. Le coller au début d'une nouvelle conversation Claude.
3. Coller le fichier de contexte thématique adapté (`contexts/*.md`).
4. Renseigner les données anonymisées de votre projet.
5. Spécifier le format de sortie attendu en vous inspirant du gabarit d'invite du fichier de contexte.
6. Procéder à la validation humaine du résultat.

### Option 2 : Configuration dans Claude Projects

1. Coller le texte de `instructions/claude-project-instructions.md` dans le champ « Project instructions » de votre projet Claude.
2. Ajouter si nécessaire `contexts/PM_CONTEXT.md` et `docs/ai-safety.md` dans la base de connaissances du projet (Project Knowledge).
3. Dans vos échanges au sein du projet, collez simplement le contexte thématique pertinent et vos données projets anonymisées et synthétisées.

---

## Schéma récapitulatif du flux de travail

```text
Exploitation avec Claude
│
├─ Conversation standard
│    └─ Coller contexts/*.md directement dans le fil de discussion
│
└─ Claude Projects
     └─ Paramétrer instructions/claude-project-instructions.md

Démarche méthodologique commune :
PM_CONTEXT.md → Fichier thématique contexts/*.md → Synthèse & Anonymisation → Validation humaine
```

---

## Bonnes pratiques pour les contextes volumineux

- Ne collez jamais de comptes rendus intégraux ou de retranscriptions brutes.
- Éliminez scrupuleusement les noms réels, entreprises et clauses contractuelles.
- Résumez au préalable vos notes brutes en 4 volets : « Faits », « Points durs », « Arbitrages ouverts », « Prochaines actions ».
- Évitez de surcharger l'invite d'historiques obsolètes : ciblez la situation active.
- La qualité de l'analyse produite dépend directement de la rigueur et de la netteté des données transmises.

---

## Sélection des contextes thématiques par cas d'usage

| Cas d'usage | Combinaison de fichiers recommandée |
|---|---|
| Bilan de santé global du projet | `contexts/PM_CONTEXT.md` + `contexts/PROJECT_HEALTH_CHECK.md` |
| Rapport d'avancement périodique | `contexts/PM_CONTEXT.md` + `contexts/STATUS_REPORT_CONTEXT.md` |
| Registre des incidents et risques | `contexts/PM_CONTEXT.md` + `contexts/ISSUE_RISK_CONTEXT.md` |
| Communication et argumentaire client | `contexts/PM_CONTEXT.md` + `contexts/CLIENT_COMMUNICATION_CONTEXT.md` |
| Gestion de crise (Premières 72h) | `contexts/PM_CONTEXT.md` + `contexts/FIRE_RESPONSE_FIRST_72H.md` |
| Gestion du changement de périmètre | `contexts/PM_CONTEXT.md` + `contexts/SCOPE_CHANGE_CONTEXT.md` |

Pour une vue d'ensemble complète, consultez [docs/use-case-map.md](../use-case-map.md).

---

## Cas pratique illustratif (Données fictives)

Exemple d'application concrète sur des données simulées :

### Scénario : Structuration du rapport d'avancement hebdomadaire

**Ressources mobilisées**
- `contexts/PM_CONTEXT.md`
- `contexts/STATUS_REPORT_CONTEXT.md`

**Données d'entrée anonymisées (Données fictives)**

```
Travaux achevés cette semaine :
- Revue de conception générale (validée)
- Déploiement de l'environnement de recette (effectif)

Travaux en cours :
- Rédaction des spécifications détaillées (avancement 70%)

Tâches en retard :
- Conception de l'interface API partenaire (2 jours de dérive)

Points durs :
- Spécifications de l'API partenaire en attente de retour client
```

**Modèle de requête (Prompt)**

```
Sur la base des contextes de référence ci-dessous, préparez le rapport d'avancement de la semaine :

【Référence PM_CONTEXT.md】
(Coller ici contexts/PM_CONTEXT.md)

【Référence STATUS_REPORT_CONTEXT.md】
(Coller ici contexts/STATUS_REPORT_CONTEXT.md)

【Situation de la semaine (Données fictives)】
(Coller ici les données d'entrée ci-dessus)

Merci de décliner la restitution selon les 3 volets :
1. Rapport d'avancement interne
2. Communication client
3. Synthèse exécutive pour la Direction
```

**Points de contrôle humain (Human Review)**
- Vérifier la parfaite exactitude des faits mentionnés.
- S'assurer que le niveau de diplomatie de la version client est adéquat.
- Valider impérativement les termes relatifs au planning, aux coûts et aux engagements contractuels.

---

## Structure de prompt recommandée pour Claude (Format balises XML)

Pour exploiter au mieux les capacités de raisonnement de Claude, structurez vos requêtes en délimitant les rôles, contextes, entrées et contraintes avec des balises XML :

```text
<task>
Définir clairement en 1 à 3 phrases le mandat confié à l'IA.
</task>
<context>
Informations méthodologiques de référence (contenu de PM_CONTEXT.md et du contexts/*.md retenu).
</context>
<input>
Données de situation du projet, notes de réunion, registre d'incidents (strictement anonymisées).
</input>
<constraints>
- Considérez les données fournies comme rigoureusement anonymisées.
- Toute déduction non étayée par les entrées doit être explicitement signalée par « (Hypothèse) ».
- En cas d'informations insuffisantes pour trancher, indiquez expressément « Données insuffisantes » ou « Les éléments fournis ne permettent pas de statuer ».
- Les sorties constituent une base d'instruction soumise à arbitrage et validation humaine préalable.
</constraints>
<output_format>
Structure attendue (ex. : Synthèse exécutive, Points durs prioritaires, Risques, Prochaines actions).
</output_format>
```

Cette structure balisée est particulièrement performante avec les modèles Claude, tout en restant pleinement compatible avec ChatGPT et Gemini.

Reportez-vous à la section « Version structurée pour Claude (Format balises XML) » présente dans chaque fichier du répertoire `contexts/`.

---

## Précautions de validation des livrables

> [!CAUTION]
> N'utilisez jamais une sortie de l'IA en production sans relecture et validation humaine préalable.

- Les réponses générées ne se substituent en aucun cas à l'arbitrage managérial.
- Tout document destiné à un client, à la direction générale ou impactant des délais/budgets doit être vérifié formellement.
- Consultez si nécessaire le directeur de projet, le PMO ou le département juridique.

---

## Documents associés

- [docs/ai-safety.md](../ai-safety.md) — Règles de sécurité et données autorisées
- [docs/legal/DISCLAIMER.md](../legal/DISCLAIMER.md) — Clause de non-responsabilité

---

## Liens utiles

- [Découvrir la boîte à outils PM × IA](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [Laboratoire PM & IA](https://techaide.jp/community/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [Diagnostic d'orientation formation](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
