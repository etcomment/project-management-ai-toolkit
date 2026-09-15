# Claude Code Skills pour PM × IA

Ce répertoire regroupe les compétences (skills) conçues pour Claude Code afin d'assister les missions de gestion de projet (PM) et le pilotage assisté par IA.

Chaque skill est constitué **exclusivement de documentation Markdown**. Il ne comporte aucun hook, commande exécutable, script shell, configuration MCP, GitHub Action, commit automatique ni déploiement automatisé.

---

## Point d'entrée recommandé

En cas d'hésitation ou pour sélectionner le contexte et le skill les plus pertinents selon votre situation, commencez par ici :

- **`pm-ai-diagnosis/SKILL.md`**
  - Qualifier la problématique PM / le cas d'usage IA et orienter vers le bon contexte ou skill
  - **Constitue le point de départ naturel pour démarrer**

---

## Détection et anticipation des risques

- **`project-risk-radar/SKILL.md`**
  - Détecter les risques implicites et les signaux faibles à partir des notes d'avancement, listes d'incidents et comptes rendus
- **`issue-risk-review/SKILL.md`**
  - Déceler les omissions dans les points de blocage et risques, identifier les tâches sans responsable ou sans échéance

---

## Prise de décision et arbitrage

- **`pm-decision-support/SKILL.md`**
  - Structurer les arbitrages du chef de projet : escalades, argumentaires client, scénarios alternatifs

---

## Communication et restitution

- **`stakeholder-strategy/SKILL.md`**
  - Adapter la stratégie de communication selon la cible : client, hiérarchie, équipe de réalisation, direction générale
- **`client-communication/SKILL.md`**
  - Préparer des projets de notes explicatives, demandes d'arbitrage et communications formelles destinées aux clients
- **`status-report/SKILL.md`**
  - Structurer les rapports d'avancement hebdomadaires/mensuels (formats interne, client et direction)

---

## Contrôle qualité et gouvernance des livrables IA

- **`ai-output-governance-review/SKILL.md`**
  - Auditer les sorties générées par l'IA avant diffusion : ton péremptoire, fuites d'informations confidentielles, engagements contractuels abusifs

---

## Gestion des réunions, du périmètre et des dérives

- **`meeting-minutes/SKILL.md`**
  - Structurer les notes de réunion en comptes rendus opérationnels : décisions actées, plans d'action (TODO), points à clarifier
- **`scope-change-review/SKILL.md`**
  - Analyser l'impact des demandes de changement de périmètre (Change Requests) : charges, délais, coûts, adhérences
- **`delay-recovery/SKILL.md`**
  - Cadrer les plans de rattrapage en cas de dérive calendaire : causes, impacts, scénarios de reprise et stratégie de communication
- **`fire-response-first-72h/SKILL.md`**
  - Conduire les 72 premières heures d'une crise projet : faits avérés, impacts, zones d'ombre et plan d'action d'urgence

---

## Revues transversales et bilans de santé

- **`pm-review/SKILL.md`**
  - Revue globale 360° du projet sous l'angle PM : avancement, incidents (issues), risques, plan d'action immédiat
- **`project-health-check/SKILL.md`**
  - Évaluer périodiquement la santé globale du projet, objectiver le niveau de criticité et prioriser les actions

---

## Précautions impératives

- Chaque skill est strictement documentaire et ne fournit aucune automatisation exécutable.
- Les sorties de l'IA ne remplacent en aucun cas l'arbitrage managérial, contractuel, juridique, calendaire ou qualité.
- Tout contenu produit doit impérativement être relu, vérifié et ajusté par un responsable humain avant diffusion.
- Ne saisissez jamais de noms de clients, noms de personnes physiques, raisons sociales, données contractuelles, clés d'API, comptes rendus intégraux non filtrés ou code de production.
- Si vous utilisez des informations de projets réels, veillez à les anonymiser, les synthétiser et les masquer rigoureusement.
- Ne contient aucun hook, commande CLI, script shell, configuration MCP, workflow GitHub Actions, commit ou déploiement automatique.

Documents associés :
- [`docs/ai-safety.md`](../../docs/ai-safety.md)
- [`docs/use-case-map.md`](../../docs/use-case-map.md)
- [`docs/tools/claude-code.md`](../../docs/tools/claude-code.md)
