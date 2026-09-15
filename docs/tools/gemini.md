# Guide d'utilisation de Google Gemini / Gemini Usage Guide

Guide pratique pour exploiter le présent référentiel avec Google Gemini.

> [!IMPORTANT]
> Ne saisissez jamais de données clients réelles, informations personnelles, clauses contractuelles ou identifiants d'accès (clés d'API, mots de passe) dans Gemini.
> Les livrables de l'IA ne remplacent pas l'arbitrage managérial. Tout contenu produit doit impérativement être relu, vérifié et ajusté par un responsable humain.

---

## `contexts/` — Composant central (AI Contexts)

Le cœur méthodologique réside dans le répertoire `contexts/`. Chaque fichier rassemble les prérequis métier, les critères d'arbitrage et les modèles d'invites (Prompt Templates).

Les gabarits d'instructions pour les paramètres système se trouvent sous `instructions/`.

---

## Fichiers de configuration système à utiliser

| Fichier | Emplacement de configuration |
|---|---|
| `instructions/gemini-instructions.md` | Champ Instructions des Gems / Préambule d'une invite |

Ce fichier fournit les directives prêtes à l'emploi à intégrer dans les paramètres d'instructions d'un Gem.

---

## Modes d'exploitation

### Option 1 : Utilisation dans une conversation standard

1. Copier le contenu de `contexts/PM_CONTEXT.md`.
2. Ouvrir une nouvelle conversation dans Gemini.
3. Coller le contenu du contexte en tête de message.
4. Ajouter à la suite le fichier de contexte thématique (`contexts/*.md`) et les informations anonymisées de votre projet.
5. Procéder à la validation humaine du résultat.

```text
Vous agirez en vous conformant strictement au contexte méthodologique ci-dessous.
Merci de structurer les éléments suivants : [Objet de votre demande].

【Cadre de référence PM_CONTEXT.md】
[Coller ici le contenu de PM_CONTEXT.md]

【Contexte thématique additionnel】
[Coller ici le contenu du fichier de contexte adapté]

【Situation du projet (Données strictement anonymisées)】
[Renseigner ici les informations du projet]
```

### Option 2 : Configuration dans les Gems de Gemini

1. Créer un nouveau Gem dans Gemini via la fonctionnalité « Gems ».
2. Coller le texte de `instructions/gemini-instructions.md` dans le champ « Instructions ».
3. Si nécessaire, insérer le socle commun `contexts/PM_CONTEXT.md` au début de vos échanges.
4. Transmettre directement les informations projets anonymisées et le contexte thématique.

> [!NOTE]
> En cas d'utilisation au sein d'un compte d'entreprise Google Workspace, vérifiez au préalable la politique de sécurité des données de votre organisation et les droits d'activation de la fonctionnalité Gems.

---

## Schéma récapitulatif du flux de travail

```text
Exploitation avec Gemini
│
├─ Conversation standard
│    └─ Coller contexts/*.md en en-tête de la conversation
│
└─ Gemini Gems
     └─ Paramétrer instructions/gemini-instructions.md

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

Pour une vue exhaustive des correspondances, consultez [docs/use-case-map.md](../use-case-map.md).

---

## Précautions spécifiques aux environnements Google Workspace

Lors de l'utilisation de Gemini dans un environnement professionnel Google Workspace, vérifiez impérativement :

- La charte interne d'utilisation de l'intelligence artificielle
- Les règles d'habilitation pour la transmission de données vers des services tiers
- La disponibilité et les autorisations de création de Gems personnalisés

En cas d'incertitude, rapprochez-vous de votre direction informatique (DSI) ou de votre responsable de la sécurité (RSSI).

---

## Exemples d'anonymisation avant saisie

| Donnée réelle (À proscrire) | Formulation anonymisée conforme |
|---|---|
| Société Alpha Solutions (Client) | Client A |
| Jean Dupont (Chef de projet client) | Intervenant A / Responsable Client |
| api_key_xxxxxxxxxx | [SUPPRIMÉ] |
| Montant contractuel : 350 000 € | Budget : Ordre de grandeur de plusieurs centaines de k€ |
| Projet Refonte Système Métier | Projet X |

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
- Typologie : Développement d'une application Web métier (au forfait)
- Phase : Conception détaillée et début de réalisation en parallèle
- Avancement global : 45%

【Situation constatée】
- La validation des spécifications d'écrans accuse 2 semaines de retard du fait du client
- Les ressources de recette ne sont pas encore affectées, plan de test non formalisé
- Le client a formulé 3 demandes d'ajouts fonctionnels sans arbitrage budgétaire
```

**Modèle de requête (Prompt)**

```
Vous agirez en vous conformant aux contextes de référence ci-dessous.
Réalisez une revue de santé (Health Check) selon une perspective Chef de Projet.
Restituez le niveau de criticité (Critique / Sous vigilance / Nominal), les risques majeurs et le plan d'action immédiat.

[Contenu de PM_CONTEXT.md]
[Contenu de PROJECT_HEALTH_CHECK.md]

【Situation du projet (Données anonymisées)】
(Coller ici les données d'entrée ci-dessus)
```

**Points de contrôle humain (Human Review)**
- Vérifier la cohérence de la note de criticité au regard des enjeux du compte.
- Réajuster la priorisation opérationnelle des actions proposées.
- Ne jamais diffuser la réponse générée directement au client ou en comité sans relecture et validation humaine préalable.

---

## Checklist de validation des résultats

- [ ] L'analyse est rigoureusement conforme à la réalité du projet
- [ ] Le registre d'expression et la tonalité respectent la relation client et interne
- [ ] Aucune formulation péremptoire n'engage imprudemment les délais, coûts ou responsabilités
- [ ] Le document a fait l'objet d'une validation par un responsable habilité avant transmission

---

## Documents associés

- [docs/ai-safety.md](../ai-safety.md) — Règles de sécurité et données autorisées
- [docs/legal/DISCLAIMER.md](../legal/DISCLAIMER.md) — Clause de non-responsabilité

---

## Liens utiles

- [Découvrir la boîte à outils PM × IA](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [Laboratoire PM & IA](https://techaide.jp/community/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [Diagnostic d'orientation formation](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
