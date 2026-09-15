# Détection des risques latents (Project Risk Radar) — Exemple pratique

## Objectif de ce cas pratique

Cet exemple illustre l'utilisation de la compétence `.claude/skills/project-risk-radar/SKILL.md` pour détecter des signaux faibles et des risques non formalisés à partir de simples notes d'avancement ou d'un registre d'alertes.

> [!IMPORTANT]
> L'ensemble des données est strictement fictif. Aucun nom réel de client, d'entreprise, d'individu ou de projet n'y figure.  
> Pour toute utilisation sur un projet réel, veillez à anonymiser et synthétiser vos données au préalable.

> [!WARNING]
> Les livrables de l'IA ne remplacent en aucun cas l'arbitrage managérial. Toute décision finale relève de la responsabilité exclusive du chef de projet.

---

## Compétence (Skill) mobilisée

- `.claude/skills/project-risk-radar/SKILL.md`

## Fichiers de contexte associés

- `contexts/PROJECT_HEALTH_CHECK.md`
- `contexts/ISSUE_RISK_CONTEXT.md`
- `contexts/DELAY_RECOVERY_CONTEXT.md`

---

## Exemples d'entrées (Input)

### Version standard

```text
En te basant sur le contenu de .claude/skills/project-risk-radar/SKILL.md,
analyse les notes d'avancement ci-dessous et fais émerger les risques opérationnels latents.

【Notes d'avancement】
- Phase actuelle : milieu de développement
- Fonctionnalité majeure A : en cours de codage, avancement à 70%
- Fonctionnalité majeure B : suspendue dans l'attente des spécifications d'API externe
- Mise à disposition de l'environnement de recette : reportée à la semaine prochaine
- Arbitrages client en souffrance : 2 maquettes d'écrans et 1 modèle de rapport d'édition
- Registre des problèmes : 3 points sur 10 sans responsable affecté
- Prochain point d'avancement : Mercredi prochain
- Échéance de livraison cible : maintenue sans décalage à ce jour
※ Noms d'acteurs, de clients et de sociétés rigoureusement anonymisés.
```

### Version structurée en balises XML (recommandée pour Claude)

```text
<task>
En te basant sur le contenu de .claude/skills/project-risk-radar/SKILL.md,
analyse les notes d'avancement ci-dessous et fais émerger les risques opérationnels latents.
</task>
<input>
【Notes d'avancement】
- Phase actuelle : milieu de développement
- Fonctionnalité majeure A : en cours de codage, avancement à 70%
- Fonctionnalité majeure B : suspendue dans l'attente des spécifications d'API externe
- Mise à disposition de l'environnement de recette : reportée à la semaine prochaine
- Arbitrages client en souffrance : 2 maquettes d'écrans et 1 modèle de rapport d'édition
- Registre des problèmes : 3 points sur 10 sans responsable affecté
- Prochain point d'avancement : Mercredi prochain
- Échéance de livraison cible : maintenue sans décalage à ce jour
</input>
<constraints>
- N'affirme aucun risque qui ne soit directement déductible des faits exposés.
- Si une déduction comporte une part d'incertitude, indique expressément « (Hypothèse) ».
- Toutes les données confidentielles ont été préalablement masquées.
- Ne conclus pas à un retard certain, mais qualifie précisément la probabilité d'occurrence et l'impact potentiel sur le calendrier.
</constraints>
```

---

## Restitution attendue de l'IA (Expected Output)

### Synthèse de détection des risques

- Identification des risques critiques : suspension du développement sur l'API externe, retard d'infrastructure de recette, accumulation des arbitrages client et carences d'assignation
- Démonstration que le maintien théorique de la date de livraison masque une dérive latente majeure sur le chemin critique

### Tableau des risques latents détectés

| Priorité | Risque détecté | Justification factuelle | Périmètre d'impact | Probabilité | Plan de maîtrise préconisé |
|---|---|---|---|---|---|
| **Haute** | Dérive calendaire par blocage d'API externe | « Fonction B : en attente des spécifications d'API » | Développement et qualification de la fonction B | Modérée à Forte | Obtenir la date ferme de remise des specs et évaluer la faisabilité d'un mock |
| **Haute** | Goulot d'étranglement sur le démarrage des tests | « Environnement de test reporté à la semaine prochaine » | Démarrage des campagnes de tests et détection des bugs | Modérée | Figer la date butoir de livraison du socle et désigner un responsable infra |
| **Moyenne** | Flottement de gouvernance sur les alertes | « 3 problèmes sur 10 sans responsable » | Traitement des anomalies opérationnelles | Modérée | Assigner impérativement un pilote et une échéance sur chaque ligne |

### Questions clés d'investigation pour le Chef de Projet

- À quelle date précise les spécifications de l'API externe seront-elles stabilisées ?
- Est-il pertinent de développer sur des bouchons d'API (mocks) provisoires pour ne pas bloquer l'équipe ?
- Le décalage de l'environnement de test amputera-t-il la durée globale de recette ?
- Qui est habilité à statuer et arbitrer sur les 3 problèmes orphelins ?

---

## Points de contrôle humain (Human Review Points)

- Les risques détectés reposent-ils sur des faits tangibles ou sur des extrapolations excessives ?
- La distinction entre faits matériels et conjectures est-elle scrupuleusement respectée ?
- Les questions de levée de doutes permettent-elles d'alimenter utilement les arbitrages internes avant toute communication client ?
- Les prévisions d'impact calendaire évitent-elles tout catastrophisme tout en posant clairement les alertes ?

---

## Ressources complémentaires recommandées

- Traitement des problèmes et risques : `contexts/ISSUE_RISK_CONTEXT.md`
- Plan de rattrapage : `contexts/DELAY_RECOVERY_CONTEXT.md`
- Aide à la décision managériale : `.claude/skills/pm-decision-support/SKILL.md`
- Stratégie par partie prenante : `.claude/skills/stakeholder-strategy/SKILL.md`
