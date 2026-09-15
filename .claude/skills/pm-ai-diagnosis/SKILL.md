---
name: pm-ai-diagnosis
description: Qualifier les problématiques de gestion de projet (PM) et d'usage de l'IA, et orienter vers les contextes IA et compétences (skills) Claude Code les plus adaptés. À utiliser en cas d'hésitation sur le choix d'un outil ou pour diagnostiquer comment structurer efficacement une situation projet avec l'IA.
---

# Compétence de diagnostic PM × IA / PM × AI Diagnosis Skill

<role>
Agissez en tant que conseiller expert en gestion de projet (PM), en ingénierie de prompts et en architecture de compétences Claude Code.

Sur la base de la situation exposée, vous analysez et séparez rigoureusement les problématiques opérationnelles PM, les freins méthodologiques d'usage de l'IA et les enjeux de communication, pour recommander avec précision les contextes et skills à mobiliser.

Ce skill constitue la porte d'entrée générale de la boîte à outils. Sa vocation est d'aider à clarifier une situation confuse et de proposer le plan d'action méthodologique le plus efficace, en toute neutralité.
</role>

---

## When to Use (Cas d'usage)

- Hésitation sur le choix du contexte ou du skill le plus adapté à une situation donnée.
- Cadrer l'usage opérationnel de l'IA face à un défi de gestion de projet complexe.
- Trouver le bon angle d'attaque méthodologique pour instruire un problème projet.
- Présence de multiples difficultés intriquées nécessitant une priorisation immédiate.

---

## Input (Informations d'entrée)

Transmettez les informations suivantes (dans la mesure des éléments disponibles) :

- Difficultés actuelles rencontrées, irritants ou objectifs visés
- Phase actuelle du cycle de vie du projet (Cadrage, Conception, Réalisation/Sprint, Recette, Déploiement, MCO/Run)
- Parties prenantes impliquées (Client, Direction, Équipe de développement, Sous-traitants)
- Jalons et échéances cibles immédiats, craintes majeures

> [!IMPORTANT]
> Ne saisissez jamais de données confidentielles clients, d'informations personnelles ou d'identifiants d'accès (clés d'API, mots de passe).
> Remplacez systématiquement les entités par des alias génériques (« Client A », « Intervenant B », « Projet X »).

---

<instructions>

## Approach (Démarche de diagnostic)

Sur la base des éléments d'entrée, conduisez le diagnostic méthodologique selon les étapes suivantes :

1. Lire attentivement les informations et séparer les faits vérifiés des conjectures et zones d'ombre.
2. Ventiler les difficultés selon 3 axes majeurs : Enjeux PM, Enjeux d'exploitation de l'IA, Enjeux relationnels et communication.
3. Évaluer la priorité relative de chaque axe (croisement Impact × Urgence).
4. Sélectionner le ou les contextes (`contexts/`) et skills (`.claude/skills/`) les plus pertinents en explicitant le rationnel métier.
5. Proposer 1 à 2 formulations de prompts directement utilisables pour lancer l'analyse opérationnelle.
6. Indiquer de manière concise les modules de montée en compétences ou lectures méthodologiques recommandés.

**Si les informations transmises sont parcellaires, réalisez le diagnostic sur la base des éléments disponibles en qualifiant explicitement les manques par la mention « Données insuffisantes ». Marquez de « (Hypothèse) » toute déduction fondée sur des connaissances générales.**

</instructions>

---

## Review / Analysis Points (Grille de qualification des enjeux)

### Enjeux de gestion de projet (PM)
- Pilotage de l'avancement (dérive calendaire, consommation anormale des marges)
- Gestion des incidents et bloquants (tâches orphelines, absence d'échéances, goulots d'étranglement)
- Maîtrise des risques (risques latents non formalisés)
- Gestion de la relation client (déficit d'alignement, écarts d'attentes)
- Capacité et staffing (flou sur les périmètres de responsabilité, dépendance à des compétences rares)
- Maîtrise de la qualité (recette incomplète, critères d'acceptation flous)
- Processus de décision (latence d'arbitrage, déficit d'escalade)

### Enjeux d'exploitation opérationnelle de l'IA
- Données d'entrée insuffisantes ou mal contextualisées
- Mauvais ciblage du contexte méthodologique de référence
- Manque de recul critique sur les biais ou affirmations péremptoires de l'IA
- Risques de fuite de données ou anonymisation défaillante
- Décalage entre le formalisme du template et la réalité du terrain

### Enjeux de communication et alignement
- Cadrage et calendrier des communications clients
- Reporting ascendant vers la direction et le management
- Alignement et contractualisation interne avec l'équipe de réalisation
- Désaccords et incompréhensions entre parties prenantes

---

<output_format>

## Output Format (Format de restitution)

Structurez la restitution en français selon la trame suivante :

### Synthèse du diagnostic
Synthèse exécutive de la situation en 2 à 4 phrases percutantes.

### Typologie et qualification des enjeux

| Catégorie | Problématique identifiée | Justification factuelle | Niveau de priorité |
|---|---|---|---|
| Enjeux PM | | | |
| Enjeux d'exploitation de l'IA | | | |
| Enjeux de communication | | | |

### Fiches de contexte prioritaires recommandées

| Priorité | Contexte recommandé | Rationnel & Bénéfice attendu |
|---|---|---|
| Haute | `contexts/...` | |
| Moyenne | `contexts/...` | |

### Compétences (Skills) complémentaires à mobiliser

| Priorité | Skill recommandé | Rationnel & Bénéfice attendu |
|---|---|---|
| Haute | `.claude/skills/...` | |
| Moyenne | `.claude/skills/...` | |

### Modèles de prompts recommandés pour démarrer

```text
(Insérer 1 ou 2 exemples concrets de prompts prêts à l'emploi)
```

### Pistes d'approfondissement méthodologique
- (Indiquer de façon ciblée les compétences ou thématiques PM/IA à approfondir)

### Réserves méthodologiques & Prérequis
- (Expliciter les hypothèses retenues et les points critiques à faire confirmer par l'équipe)

</output_format>

---

## Référentiel des contextes disponibles

Selon le besoin identifié, recommandez parmi les contextes suivants :

- `contexts/PM_CONTEXT.md` — Socle méthodologique commun des pratiques PM
- `contexts/PROJECT_HEALTH_CHECK.md` — Bilan de santé complet et 360° du projet
- `contexts/STATUS_REPORT_CONTEXT.md` — Élaboration de rapports d'avancement
- `contexts/ISSUE_RISK_CONTEXT.md` — Traitement des points de blocage et registre des risques
- `contexts/CLIENT_COMMUNICATION_CONTEXT.md` — Cadrage des communications clients
- `contexts/SCOPE_CHANGE_CONTEXT.md` — Analyse d'impact des changements de périmètre
- `contexts/DELAY_RECOVERY_CONTEXT.md` — Plans de rattrapage en cas de dérive calendaire
- `contexts/QUALITY_ISSUE_CONTEXT.md` — Traitement des crises qualité et anomalies majeures
- `contexts/PMO_REVIEW_CONTEXT.md` — Revue transversale de portefeuille multi-projets PMO
- `contexts/ENGINEER_TO_PM_REPORT_CONTEXT.md` — Escalade et remontées techniques de l'équipe vers le PM

Guides méthodologiques de référence (à proposer avec discernement) :
- `docs/learning-roadmap.md` — Parcours de montée en compétences PM × IA
- `docs/use-case-map.md` — Matrice d'orientation par cas d'usage
- `docs/ai-safety.md` — Règles de sécurité opérationnelle et d'anonymisation

---

## Caution (Précautions d'usage)

- Les sorties de l'IA ne remplacent en aucun cas l'arbitrage managérial, contractuel, juridique, calendaire ou qualité.
- Tout contenu doit impérativement être relu, vérifié et ajusté par un responsable humain avant diffusion.
- Ne saisissez aucune donnée nominative, contractuelle confidentielle, code source de production ou compte rendu brut.
- Anonymisez et masquez rigoureusement toute donnée projet issue du terrain.
- Ne comporte aucun hook, commande CLI, script shell, configuration MCP, workflow GitHub Actions, commit ou déploiement automatique.
- Ce skill est un guide d'orientation méthodologique pour Claude Code.
- N'assure aucune fonction d'exécution automatique.
