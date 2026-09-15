# Diagnostic PM × IA — Exemple pratique d'utilisation

## Objectif de ce cas pratique

Cet exemple illustre l'utilisation de la compétence `.claude/skills/pm-ai-diagnosis/SKILL.md` pour catégoriser et résoudre méthodiquement les enjeux de gestion de projet (PM), les défis d'adoption de l'IA et les difficultés de communication avec les parties prenantes.

> [!IMPORTANT]
> L'ensemble des données est strictement fictif. Aucun nom réel de client, d'entreprise, d'individu ou de projet n'y figure.  
> Pour toute utilisation sur un projet réel, veillez à anonymiser et synthétiser vos données au préalable.

> [!WARNING]
> Les livrables de l'IA ne remplacent en aucun cas l'arbitrage managérial. Toute décision finale relève de la responsabilité exclusive du chef de projet.

---

## Compétence (Skill) mobilisée

- `.claude/skills/pm-ai-diagnosis/SKILL.md`

## Fichiers de contexte associés

- `contexts/PM_CONTEXT.md`
- `contexts/PROJECT_HEALTH_CHECK.md`
- `contexts/STATUS_REPORT_CONTEXT.md`
- `contexts/ISSUE_RISK_CONTEXT.md`
- `contexts/CLIENT_COMMUNICATION_CONTEXT.md`

---

## Exemples d'entrées (Input)

### Version standard

```text
En te basant sur le contenu de .claude/skills/pm-ai-diagnosis/SKILL.md,
indique-moi les contextes et compétences les plus adaptés pour traiter la situation ci-dessous.

【Situation opérationnelle】
Nous sommes actuellement en milieu de phase de développement.
Les développements avancent, mais plusieurs spécifications en attente de validation client restent bloquées. J'hésite sur le niveau de détail et la posture à adopter dans le rapport d'avancement hebdomadaire.
Le registre des alertes compte 10 problèmes recensés, dont certains sans responsable ni échéance définis.
Je souhaite utiliser l'IA pour remettre de l'ordre dans ce pilotage, mais j'ignore quel fichier de contexte exploiter en priorité.
※ Les noms de clients, d'entreprises et données sensibles ont été rigoureusement anonymisés.
```

### Version structurée en balises XML (recommandée pour Claude)

```text
<task>
En te basant sur le contenu de .claude/skills/pm-ai-diagnosis/SKILL.md,
indique-moi les contextes et compétences les plus adaptés pour traiter la situation ci-dessous.
</task>
<input>
【Situation opérationnelle】
Nous sommes actuellement en milieu de phase de développement.
Les développements avancent, mais plusieurs spécifications en attente de validation client restent bloquées. J'hésite sur le niveau de détail et la posture à adopter dans le rapport d'avancement hebdomadaire.
Le registre des alertes compte 10 problèmes recensés, dont certains sans responsable ni échéance définis.
Je souhaite utiliser l'IA pour remettre de l'ordre dans ce pilotage, mais j'ignore quel fichier de contexte exploiter en priorité.
</input>
<constraints>
- Toutes les données nominatives et sensibles ont été préalablement anonymisées.
- En cas d'informations manquantes pour étayer le diagnostic, mentionne expressément « Données insuffisantes ».
- Explicite systématiquement la justification opérationnelle de chaque contexte ou compétence recommandé.
</constraints>
```

---

## Restitution attendue de l'IA (Expected Output)

La restitution attendue doit structurer la réflexion selon les axes suivants :

### Synthèse du diagnostic

- Ventilation claire entre problématiques PM pures, freins d'usage de l'IA et défis de communication
- Identification du contexte IA prioritaire à instancier en premier
- Recommandation des compétences Claude Code à activer en synergie

### Typologie et ventilation des problématiques

| Typologie | Nature de l'enjeu | Niveau de priorité |
|---|---|---|
| **Enjeu PM** | Spécifications en souffrance côté client ; registre des problèmes comportant des points sans responsable ni échéance | Haute |
| **Enjeu d'usage de l'IA** | Difficulté à sélectionner le contexte adapté à la problématique immédiate | Moyenne |
| **Enjeu de communication** | Incertitude sur le niveau de granularité et la posture diplomatique dans le rapport hebdomadaire | Haute |

### Contextes prioritaires à exploiter

| Priorité | Fichier de contexte | Justification opérationnelle |
|---|---|---|
| **Haute** | `contexts/ISSUE_RISK_CONTEXT.md` | Pour assainir le registre des problèmes et assigner responsables et échéances fermes |
| **Haute** | `contexts/STATUS_REPORT_CONTEXT.md` | Pour calibrer distinctement le rapport d'avancement interne et la note client |
| **Moyenne** | `contexts/CLIENT_COMMUNICATION_CONTEXT.md` | Pour formaliser des relances fermes sans heurter la relation partenariale |

### Compétences (Skills) à mobiliser en complément

| Priorité | Compétence | Justification opérationnelle |
|---|---|---|
| **Haute** | `issue-risk-review` | Pour auditer et fiabiliser la couverture du tableau des problèmes |
| **Haute** | `status-report` | Pour structurer la synthèse exécutive et le flash report hebdomadaire |
| **Moyenne** | `stakeholder-strategy` | Pour adapter le discours selon les profils d'interlocuteurs (direction vs opérationnels) |

---

## Points de contrôle humain (Human Review Points)

- Le diagnostic reflète-t-il la dynamique réelle et les urgences du projet ?
- Les contextes préconisés répondent-ils directement aux goulots d'étranglement constatés ?
- Un chef de projet a-t-il relu et adapté les livrables avant toute diffusion interne ou client ?
- Aucune information confidentielle ou nominative n'a-t-elle été injectée par inadvertance ?

---

## Ressources complémentaires recommandées

- Cartographie des cas d'usage : `docs/use-case-map.md`
- Parcours d'apprentissage : `docs/learning-roadmap.md`
- Consignes de sécurité et gouvernance : `docs/ai-safety.md`
