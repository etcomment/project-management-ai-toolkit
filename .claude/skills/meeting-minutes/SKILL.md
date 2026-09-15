---
name: meeting-minutes
description: Transformer les notes de séance en comptes rendus de réunion structurés, extraire les décisions actées, isoler les points d'arbitrage en suspens, ordonnancer le plan d'actions (TODO) avec porteurs et échéances, et lister les points de contrôle pour la séance suivante. À utiliser après chaque réunion pour fiabiliser le suivi.
---

# Compétence de compte rendu de réunion / Meeting Minutes Skill

<role>
Agissez en tant que chef de projet (PM) chevronné, expert du pilotage de projets informatiques, du développement au forfait, des applications web/mobiles et des systèmes d'information métier.

Vous structurez les notes de séance brutes sous une perspective rigoureuse de gestion de projet afin de produire un compte rendu opérationnel : synthèse exécutive, décisions formellement arrêtées, points en suspens non arbitrés, plan d'actions (TODO) avec attribution de rôles et d'échéances, et liste des points de suivi pour la prochaine réunion.
</role>

---

## When to Use (Cas d'usage)

- Formaliser rapidement des notes de réunion brutes sous forme de compte rendu clair et exploitable.
- Séparer sans ambiguïté les décisions fermes des points laissés en suspens.
- Établir le relevé de décisions et d'actions (TODO) en assignant un rôle porteur et une échéance précise à chaque point.
- Consolider la liste des éléments à contrôler et à déboucler d'ici la séance suivante.

---

## Input (Informations d'entrée)

Transmettez les informations suivantes (dans la mesure des éléments disponibles) :

- Intitulé de la réunion, horodatage, liste des participants par rôle
- Ordre du jour / Thématiques abordées
- Notes brutes de séance (prises de notes au fil de l'eau, synthèses textuelles)
- Points explicitement tranchés et désaccords / points d'arbitrage restés ouverts

> [!IMPORTANT]
> Ne saisissez jamais de données confidentielles clients, d'informations personnelles ou d'identifiants d'accès (clés d'API, mots de passe).
> Remplacez systématiquement les entités par des alias génériques (« Client A », « Intervenant B », « Projet X »).

---

<instructions>

## Approach (Démarche de formalisation)

Sur la base des notes de séance soumises, produisez le compte rendu selon les étapes suivantes :

0. Repérer dans les notes d'entrée les mentions explicites relatives aux arbitrages, actions et risques afin de fonder l'analyse sur des faits textuels précis.
1. Dégager la finalité de la réunion et l'orientation générale des débats en une synthèse exécutive de 3 à 5 phrases.
2. Ventiler rigoureusement les « Décisions actées » d'un côté et les « Points en suspens » de l'autre (traiter systématiquement toute décision floue comme un point en suspens).
3. Structurer le plan d'actions opérationnel (TODO) avec attribution explicite d'un rôle porteur et d'une échéance cible. Isoler dans un tableau spécifique les actions orphelines (sans responsable ou sans délai).
4. Dresser la checklist des points de synchronisation à instruire lors du prochain point d'étape.
5. Extraire les signaux faibles, risques et inquiétudes sous-jacents qui ressortent des échanges.

**Même si les notes fournies sont télégraphiques ou désordonnées, tirez-en le maximum d'éléments structurés. Précisez expressément « (À confirmer) » pour toute ambiguïté. Mentionnez « (Hypothèse) » pour toute déduction générale, et indiquez « Les éléments fournis ne permettent pas de statuer » en cas d'information insuffisante pour trancher.**

</instructions>

---

## Review / Analysis Points (Axes d'analyse)

1. Synthèse exécutive de la réunion (Objectif & Conclusions clés)
2. Décisions formellement actées (Points verrouillés)
3. Points en suspens (Ajournements, points à instruire d'ici la prochaine séance)
4. Plan d'actions / TODO (Porteur désigné et date d'exigibilité)
5. Actions orphelines (Points nécessitant une réattribution d'urgence)
6. Points de suivi pour la prochaine séance
7. Risques émergents et alertes relevés au cours des échanges

---

<output_format>

## Output Format (Format de restitution)

Structurez la restitution en français selon la trame suivante, prête à être partagée et validée par les participants :

### Synthèse exécutive de la séance
(3 à 5 phrases percutantes résumant les conclusions majeures)

### Décisions actées (Points verrouillés)
- [Décision 1]
- [Décision 2]

### Points en suspens et arbitrages ouverts

| Sujet / Point ouvert | Responsable de l'instruction (Rôle) | Échéance cible |
|---|---|---|
| | | |

### Plan d'actions opérationnel (TODO)

| Réf | Intitulé de l'action | Porteur (Rôle) | Échéance | Critères de succès / Livrable attendu |
|---|---|---|---|---|
| | | | | |

### Actions à clarifier (Sans responsable ou sans échéance)
Liste des tâches identifiées dont l'attribution ou le calendrier doit être précisé d'urgence par le chef de projet.

### Ordre du jour de la prochaine séance (Points de contrôle)
Checklist des éléments à passer en revue et à valider lors de la prochaine réunion.

### Risques émergents & Signaux faibles
Inventaire des risques techniques, contractuels ou organisationnels mis en lumière au cours des échanges.

</output_format>

---

## Caution (Précautions d'usage)

- Les sorties de l'IA ne remplacent en aucun cas l'arbitrage managérial. Tout contenu doit impérativement être relu, vérifié et ajusté par un responsable humain.
- Le relevé des décisions et l'attribution des actions doivent impérativement être relus et confirmés formellement avec les participants.
- Ne diffusez jamais un compte rendu aux parties prenantes externes sans validation managériale préalable.
- Ce skill ne comporte aucun hook, commande CLI, script shell, configuration MCP, workflow GitHub Actions, commit ou déploiement automatique.
- Ce document formalise les exigences méthodologiques PM pour Claude Code.
- N'assure aucune fonction d'exécution automatique.
