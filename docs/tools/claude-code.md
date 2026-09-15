# Guide Claude Code / Claude Code Guide

Guide pratique pour exploiter le présent référentiel avec Claude Code en environnement terminal.

> [!IMPORTANT]
> Ne saisissez jamais de données confidentielles clients, d'informations personnelles ou d'identifiants d'accès (clés d'API, mots de passe) dans Claude Code.
> Les livrables de l'IA ne remplacent en aucun cas l'arbitrage managérial. Tout contenu produit doit impérativement être relu, vérifié et ajusté par un responsable humain.

---

## `contexts/` — Composant central (AI Contexts)

Le cœur méthodologique réside dans le répertoire `contexts/`.

Les compétences méthodologiques adaptées à Claude Code sont regroupées sous `.claude/skills/`.

---

## Organisation de l'arborescence des Skills

```text
.claude/
└─ skills/
   ├─ README.md                          ← Sommaire général et guide des compétences
   │
   ├─ pm-ai-diagnosis/SKILL.md           ← Point d'entrée : diagnostic du besoin et orientation
   │
   ├─ project-risk-radar/SKILL.md        ← Détection et anticipation des risques
   ├─ issue-risk-review/SKILL.md
   │
   ├─ pm-decision-support/SKILL.md       ← Aide à la décision et arbitrage
   │
   ├─ stakeholder-strategy/SKILL.md      ← Stratégie de communication et alignement
   ├─ client-communication/SKILL.md
   ├─ status-report/SKILL.md
   │
   ├─ ai-output-governance-review/SKILL.md  ← Contrôle qualité et gouvernance des sorties IA
   │
   ├─ meeting-minutes/SKILL.md           ← Réunions, changements de périmètre et crises
   ├─ scope-change-review/SKILL.md
   ├─ delay-recovery/SKILL.md
   ├─ fire-response-first-72h/SKILL.md
   │
   ├─ pm-review/SKILL.md                 ← Revues transversales et bilans de santé
   └─ project-health-check/SKILL.md
```

---

## Nature et portée des Skills

Les compétences de ce répertoire sont **exclusivement documentaires**. Elles ne comportent aucun des composants techniques suivants :

| Composant exclu | Justification |
|---|---|
| Hooks exécutables | Prévention de toute exécution automatique non sollicitée |
| Commandes CLI automatiques | Prévention de toute action système autonome |
| Scripts shell | Prévention de tout impact système imprévu |
| Configurations MCP | Absence de couplage automatique avec des services externes |
| Workflows GitHub Actions | Prévention de déclenchements automatiques en CI/CD |
| Commits et déploiements automatiques | Protection contre toute modification non validée du code et de la production |

Ces compétences formalisent les exigences de rigueur et les grilles de lecture de gestion de projet (PM) pour orienter le raisonnement de Claude Code.

---

## Matrice de sélection des Skills

### Point d'entrée recommandé

| Objectif visé | Fichier Skill |
|---|---|
| Diagnostiquer la situation et choisir le bon contexte ou skill | `.claude/skills/pm-ai-diagnosis/SKILL.md` |

### Détection et anticipation des risques

| Objectif visé | Fichier Skill |
|---|---|
| Détecter les risques sous-jacents et les signaux faibles | `.claude/skills/project-risk-radar/SKILL.md` |
| Auditer la complétude du registre des incidents et des risques | `.claude/skills/issue-risk-review/SKILL.md` |

### Aide à la décision et arbitrage

| Objectif visé | Fichier Skill |
|---|---|
| Structurer un arbitrage managérial complexe (escalade, choix A/B) | `.claude/skills/pm-decision-support/SKILL.md` |

### Communication et restitution

| Objectif visé | Fichier Skill |
|---|---|
| Définir la stratégie et le séquençage de communication par cible | `.claude/skills/stakeholder-strategy/SKILL.md` |
| Préparer un projet de courriel ou d'explication client | `.claude/skills/client-communication/SKILL.md` |
| Structurer le rapport d'avancement périodique | `.claude/skills/status-report/SKILL.md` |

### Contrôle qualité et gouvernance des sorties IA

| Objectif visé | Fichier Skill |
|---|---|
| Auditer la sécurité et le ton des textes produits par l'IA avant diffusion | `.claude/skills/ai-output-governance-review/SKILL.md` |

### Réunions, changements et gestion des dérives

| Objectif visé | Fichier Skill |
|---|---|
| Rédiger le compte rendu, les décisions et le plan d'actions (TODO) | `.claude/skills/meeting-minutes/SKILL.md` |
| Qualifier les impacts d'un changement de périmètre (Scope Change) | `.claude/skills/scope-change-review/SKILL.md` |
| Établir les scénarios d'un plan de rattrapage calendaire | `.claude/skills/delay-recovery/SKILL.md` |
| Conduire le plan d'action d'urgence des premières 72h de crise | `.claude/skills/fire-response-first-72h/SKILL.md` |

### Revues transversales et bilans de santé

| Objectif visé | Fichier Skill |
|---|---|
| Revue globale 360° du projet sous l'angle PM | `.claude/skills/pm-review/SKILL.md` |
| Bilan de santé opérationnel (Health Check) | `.claude/skills/project-health-check/SKILL.md` |

---

## Exemples concrets d'utilisation

Dans l'interface de conversation de Claude Code, formulez vos demandes selon les modèles suivants :

### Exemple 1 : Revue du README sous l'angle PM

```text
En vous conformant aux directives de .claude/skills/pm-review/SKILL.md,
réalisez une revue critique du fichier README.md selon une perspective Chef de Projet.
```

### Exemple 2 : Préparation du rapport d'avancement

```text
En vous appuyant sur .claude/skills/status-report/SKILL.md,
structurez la situation d'avancement ci-dessous en version interne et en version client.

【Situation de la semaine (Données anonymisées)】
(Coller ici les données)
```

### Exemple 3 : Audit du registre des incidents et des risques

```text
Sur la base de .claude/skills/issue-risk-review/SKILL.md,
examinez notre registre d'incidents actuel selon une perspective Chef de Projet.
Identifiez les tâches orphelines, les dates manquantes et les points nécessitant une escalade.
```

### Exemple 4 : Diagnostic d'orientation et choix de contexte

```text
<task>
En vous appuyant sur .claude/skills/pm-ai-diagnosis/SKILL.md,
recommandez le contexte et le skill les plus pertinents pour la situation suivante.
</task>
<input>
【Situation constatée】
J'hésite entre préparer le rapport hebdomadaire, organiser l'explication client ou revoir la gestion des incidents.
Les développements avancent mais les validations client en attente s'accumulent, et je n'ai pas encore arrêté les sujets à aborder lors du prochain comité.
</input>
<constraints>
- L'ensemble des données d'entrée est strictement anonymisé.
- Mentionnez expressément « Données insuffisantes » si une information manque pour conclure.
</constraints>
```

### Exemple 5 : Détection des signaux faibles et risques latents

```text
<task>
En vous conformant à .claude/skills/project-risk-radar/SKILL.md,
détectez les signaux faibles et risques sous-jacents à partir des notes d'avancement ci-dessous.
</task>
<input>
【Notes d'avancement】
- Spécifications de l'API partenaire en cours d'analyse
- Déploiement de l'environnement de recette décalé à la semaine prochaine
- 3 demandes de modifications fonctionnelles en attente d'arbitrage client
- L'équipe priorise l'implémentation des écrans principaux
- Point d'avancement prévu au prochain comité
</input>
<constraints>
- Ne formulez aucune affirmation péremptoire non étayée par les données d'entrée.
- Mentionnez « (Hypothèse) » pour toute déduction générale.
- Données strictement anonymisées.
</constraints>
```

### Exemple 6 : Structuration d'un arbitrage managérial complexe

```text
<task>
En vous appuyant sur .claude/skills/pm-decision-support/SKILL.md,
instruisez l'arbitrage ci-dessous : options possibles, critères de choix, recommandation et opportunité d'escalade.
</task>
<input>
【Problématique d'arbitrage】
Les spécifications de l'API externe n'étant pas stabilisées côté client, faut-il engager une implémentation simulée (mock) ou suspendre le chantier jusqu'à confirmation définitive ?
【Situation】
- Attendre décalera mécaniquement le lancement de la recette
- Une implémentation simulée comporte un risque de refactorisation ultérieure (rework)
- La date de livraison contractuelle reste inchangée à ce jour
- La direction de projet n'a pas encore été saisie
</input>
<constraints>
- Formulez l'analyse sous forme d'aide à la décision, l'arbitrage final revenant au responsable humain.
- Ne posez aucun engagement ferme sur les délais, les coûts ou les responsabilités.
- Mentionnez explicitement les zones de flou le cas échéant.
</constraints>
```

### Exemple 7 : Revue de gouvernance d'un projet de texte client

```text
<task>
En vous conformant à .claude/skills/ai-output-governance-review/SKILL.md,
auditez le projet de texte destiné au client ci-dessous : décelez les promesses excessives, omissions, risques de fuites ou engagements contractuels imprudents.
</task>
<input>
【Texte à auditer】
À ce jour, aucun impact n'est à déplorer sur la date de livraison finale.
Dès stabilisation des spécifications de l'API partenaire, nous procéderons aux développements sans délai.
Concernant les demandes d'ajouts formulées, nous les intégrerons dans le planning actuel sans surcoût.
【Finalité】
Projet de note d'avancement hebdomadaire pour le client
</input>
<constraints>
- Auditez le texte avec l'exigence d'une communication client formelle (maîtrise des risques, posture, omissions).
- Ne posez aucune conclusion péremptoire de « conformité juridique totale ».
- Préconisez formellement la validation de la direction de projet et des services juridiques.
</constraints>
```

---

## Articulation entre `contexts/` et les Skills Claude Code

Les compétences Claude Code et les fichiers de contexte se complètent naturellement :

- `contexts/*.md` : Référentiels méthodologiques universels et modèles de requêtes (communs à ChatGPT, Gemini, Claude et Claude Code).
- `.claude/skills/*.md` : Guides de raisonnement spécifiques fournissant à Claude Code les grilles d'analyse PM.

Avec Claude Code, l'association d'un Skill et de `contexts/PM_CONTEXT.md` garantit une pertinence d'analyse maximale :

```text
Après avoir chargé .claude/skills/pm-review/SKILL.md et contexts/PM_CONTEXT.md,
réalisez une revue de situation complète de ce référentiel selon une perspective Chef de Projet.
```

---

## Précautions impératives

- Les fichiers `SKILL.md` sont des canevas documentaires : prenez le temps de vous les approprier.
- **Ne saisissez jamais d'informations confidentielles, données personnelles ou identifiants techniques dans Claude Code.**
- Les sorties de l'IA ne remplacent en aucun cas l'arbitrage managérial ou légal.
- Tout contenu destiné à un client ou à la gouvernance interne requiert impérativement une relecture humaine préalable.
- Vérifiez au préalable vos paramètres de confidentialité et d'utilisation des données sur Claude Code.

---

## Documents associés

- [docs/ai-safety.md](../ai-safety.md) — Règles de sécurité et données autorisées
- [docs/legal/DISCLAIMER.md](../legal/DISCLAIMER.md) — Clause de non-responsabilité

---

## Liens utiles

- [Découvrir la boîte à outils PM × IA](https://techaide.jp/ai-toolkit/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [Laboratoire PM & IA](https://techaide.jp/community/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
- [Diagnostic d'orientation formation](https://techaide.jp/course-diagnosis/?utm_source=github&utm_medium=repo&utm_campaign=pm_ai_toolkit)
