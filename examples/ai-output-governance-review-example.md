# Revue de gouvernance des livrables IA (AI Output Governance Review) — Exemple pratique

## Objectif de ce cas pratique

Cet exemple illustre l'utilisation de la compétence `.claude/skills/ai-output-governance-review/SKILL.md` pour auditer et sécuriser un projet de communication client rédigé par une IA avant toute émission formelle.

> [!IMPORTANT]
> L'ensemble des données est strictement fictif. Aucun nom réel de client, d'entreprise, d'individu ou de projet n'y figure.  
> Pour toute utilisation sur un projet réel, veillez à anonymiser et synthétiser vos données au préalable.

> [!WARNING]
> Les livrables de l'IA ne remplacent en aucun cas l'arbitrage managérial. Toute décision finale relève de la responsabilité exclusive du chef de projet.

---

## Compétence (Skill) mobilisée

- `.claude/skills/ai-output-governance-review/SKILL.md`

## Fichiers de contexte associés

- `contexts/CLIENT_COMMUNICATION_CONTEXT.md`
- `contexts/STATUS_REPORT_CONTEXT.md`
- `docs/ai-safety.md`

---

## Exemples d'entrées (Input)

### Version standard

```text
En te basant sur les directives de .claude/skills/ai-output-governance-review/SKILL.md,
analyse le projet de message client ci-dessous et identifie toute formulation péremptoire risquée, divulgation confidentielle, absence de vérification préalable ou engagement inconsidéré sur les délais, les coûts et le périmètre contractuel.

【Projet de message à auditer】
À ce jour, il n'y a aucun impact sur la date de livraison.
Dès que les spécifications de l'API externe seront validées, nous déploierons l'implémentation comme prévu.
Concernant vos demandes complémentaires, nous serons en mesure de les intégrer dans le calendrier actuel.
La qualité est également sous contrôle, la mise en production s'effectuera sans encombre à la date prévue.

【Contexte d'utilisation】
Brouillon pour le rapport d'avancement hebdomadaire transmis au client
※ Noms d'acteurs, de clients et de sociétés rigoureusement anonymisés.
```

### Version structurée en balises XML (recommandée pour Claude)

```text
<task>
En te basant sur les directives de .claude/skills/ai-output-governance-review/SKILL.md,
analyse le projet de message client ci-dessous et identifie toute formulation péremptoire risquée, divulgation confidentielle, absence de vérification préalable ou engagement inconsidéré sur les délais, les coûts et le périmètre contractuel.
</task>
<input>
【Projet de message à auditer】
À ce jour, il n'y a aucun impact sur la date de livraison.
Dès que les spécifications de l'API externe seront validées, nous déploierons l'implémentation comme prévu.
Concernant vos demandes complémentaires, nous serons en mesure de les intégrer dans le calendrier actuel.
La qualité est également sous contrôle, la mise en production s'effectuera sans encombre à la date prévue.

【Contexte d'utilisation】
Brouillon pour le rapport d'avancement hebdomadaire transmis au client
</input>
<constraints>
- Évalue la communication en considérant qu'elle sera remise directement au client (exigences maximales de sécurité juridique et de prudence).
- N'affirme jamais de manière péremptoire qu'un texte est « parfaitement conforme sur le plan légal » ou « sans risque contractuel ».
- Rappelle expressément la nécessité de validations hiérarchiques ou juridiques lorsque la situation le commande.
- Les données sensibles ont été préalablement masquées.
</constraints>
```

---

## Restitution attendue de l'IA (Expected Output)

### Synthèse de la revue de gouvernance

| Critère | Évaluation |
|---|---|
| **Diffusable en l'état ?** | **Non — Modifications obligatoires requises** |
| **Motif principal** | Formulations péremptoires constituant des engagements fermes et imprudents sur les délais, la prise en charge gratuite d'évolutions et la garantie de qualité sans réserve. |

### Formulations à corriger et risques associés

| Formulation initiale | Risque opérationnel & juridique | Proposition de reformulation prudente |
|---|---|---|
| *« À ce jour, il n'y a aucun impact sur la date de livraison »* | Affirmation péremptoire engageant la responsabilité en cas de dérive ultérieure | *« À ce stade, aucun impact majeur n'a été caractérisé, sous réserve de la stabilisation rapide des spécifications d'API externe qui demeure sous surveillance étroite. »* |
| *« Concernant vos demandes complémentaires, nous serons en mesure de les intégrer dans le calendrier actuel »* | Acceptation unilatérale et sans frais d'une extension de périmètre | *« Concernant les évolutions sollicitées, nous finalisons l'instruction de leur périmètre et de leurs impacts afin de convenir avec vous des modalités de prise en compte. »* |
| *« La qualité est également sous contrôle, la mise en production s'effectuera sans encombre »* | Engagement de résultat et garantie implicite sans réserve | *« Les contrôles effectués à ce stade ne révèlent pas d'anomalie critique bloquante pour la poursuite des étapes d'homologation. »* |

### Vérifications préalables indispensables avant émission au client

- Date ferme d'arbitrage des spécifications de l'API externe
- Bilan d'impact consolidé des demandes complémentaires (charges et calendrier)
- Arbitrage hiérarchique interne sur la politique contractuelle applicable aux demandes d'évolution
- Vérification du respect des clauses contractuelles et conditions générales applicables

---

## Points de contrôle humain (Human Review Points)

- Le message évite-t-il toute promesse implicite ou garantie non étayée ?
- Les affirmations relatives aux délais, à la qualité, aux coûts et aux responsabilités sont-elles rigoureusement nuancées ?
- Les arbitrages nécessitant l'aval de la direction ou du service juridique ont-ils été instruits ?
- Aucune donnée confidentielle ou non communicable n'est-elle mentionnée ?

---

## Ressources complémentaires recommandées

- Guide de sécurité et d'éthique de l'IA : `docs/ai-safety.md`
- Communication avec les clients : `contexts/CLIENT_COMMUNICATION_CONTEXT.md`
- Stratégie d'alignement par partie prenante : `.claude/skills/stakeholder-strategy/SKILL.md`
