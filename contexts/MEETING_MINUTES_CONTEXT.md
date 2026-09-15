# Contexte de création de compte-rendu / Meeting Minutes Context

---

## Purpose (objectif de ce contexte)

Ce contexte permet à l'IA d'organiser, à partir des notes de réunion, des déclarations orales, des décisions apparentes et des points en attente, un compte-rendu de réunion, une liste de tâches à faire et une liste de points à vérifier lors de la prochaine réunion.

**L'IA ne remplace pas la décision du PM.** L'IA aide à structurer, classifier et créer des brouillons de compte-rendu. La décision finale doit toujours être prise par un humain.

> [!CAUTION]
> Ne transmettez pas de noms réels de participants, de clients, de sociétés ou de personnes permettant une identification directe à l'IA.
> Si le contenu de la réunion contient des informations contractuelles, d'authentification ou confidentielles, masquez-les ou excluez-les.

---

## Use Case (scénarios d'utilisation)

- Créer un compte-rendu de réunion à partir de notes manuscrites
- Séparer les décisions apparentes des points en attente dans le contenu des déclarations
- Extraire une liste de tâches avec responsables et délais
- Organiser les points à vérifier lors de la prochaine réunion
- Identifier les risques ou points de vigilance à partir des notes de réunion

---

## Input (informations à transmettre à l'IA)

Après avoir chargé ce contexte, transmettez (en masquant les informations confidentielles et les données personnelles) :

```
### Objectif de la réunion
(Exemple : réunion hebdomadaire, validation des exigences, revue de conception, réunion de gestion d'incident, etc.)

### Type de réunion
(Exemple : réunion interne régulière, réunion client régulière, revue interne, réunion de lancement, etc.)

### Rôles des participants (sans les noms réels)
(Exemple : PM, responsable développement, responsable infrastructure, contact client A, etc.)

### Notes de réunion et déclarations orales (informations confidentielles masquées)
(Listes à puces ou mémos bruts à copier tels quels)

### Contenu pouvant ressembler à une décision
(Éléments qui semblent avoir été confirmés sous forme de liste à puces)

### Points en attente
(Éléments encore en discussion ou reportés)

### Contenu pouvant ressembler à une tâche
(Éléments que quelqu'un a dit qu'il ferait ou qui semblent devoir être faits)

### Points à vérifier lors de la prochaine réunion
(Éléments que vous souhaitez vérifier lors de la prochaine réunion)
```

---

## Output (résultat attendu de l'IA)

### 1. Synthèse de la réunion

Vue d'ensemble de l'objectif et du résultat de la réunion (3 à 5 lignes environ).

### 2. Décisions prises

Liste des éléments confirmés lors de la réunion.

### 3. Points en attente

Liste des éléments encore en discussion ou reportés.

### 4. Liste des tâches

| No. | Contenu de la tâche | Responsable (rôle) | Délai | Remarques |
|---|---|---|---|---|

### 5. Tâches sans responsable assigné

Liste des tâches dont le responsable n'est pas défini ou est peu clair.

### 6. Points à vérifier lors de la prochaine réunion

Liste des éléments à vérifier lors de la prochaine réunion.

### 7. Risques et points de vigilance

Identification des risques ou points de vigilance à partir des notes de réunion.

---

## Caution (précautions d'utilisation)

- **Ne transmettez pas de noms réels de participants, de clients, de sociétés ou de personnes permettant une identification directe à l'IA.** Utilisez plutôt leurs rôles (PM, contact client A, etc.).
- Le compte-rendu généré par l'IA est un brouillon. Vérifiez toujours la concordance avec les faits avant utilisation.
- Le compte-rendu destiné au client ne doit pas être utilisé tel quel : il doit être vérifié et corrigé par un humain avant envoi.
- Ne transmettez pas à l'IA de contenus incluant des informations contractuelles, d'authentification ou confidentielles.
- **L'IA ne remplace pas la décision du PM.** La décision finale doit toujours être prise par un humain.

---

## Exemple d'utilisation (template)

```text
Basé sur ce contexte, organisez les notes de réunion en compte-rendu, liste de tâches et points à vérifier.

## Contexte

[Collez ici le contenu de PM_CONTEXT.md]
[Collez ici le contenu de MEETING_MINUTES_CONTEXT.md]

---

## Informations sur la réunion (informations confidentielles masquées)

### Objectif de la réunion
(Entrez)

### Type de réunion
(Entrez)

### Rôles des participants (sans les noms réels)
(Entrez)

### Notes de réunion et déclarations orales
(Entrez)

### Contenu pouvant ressembler à une décision
(Entrez)

### Points en attente
(Entrez)

### Contenu pouvant ressembler à une tâche
(Entrez)

### Points à vérifier lors de la prochaine réunion
(Entrez)

---

## Résultat attendu

1. Synthèse de la réunion (3~5 lignes)
2. Liste des décisions prises
3. Liste des points en attente
4. Liste des tâches (responsable, délai, remarques)
5. Liste des tâches sans responsable assigné
6. Points à vérifier lors de la prochaine réunion
7. Risques et points de vigilance

※ Le résultat de l'IA est un brouillon. La décision finale doit toujours être prise par un humain.
※ La validation humaine est requise avant l'envoi au client ou le reporting interne.
```

---

## Exemple d'utilisation pour Claude (version XML)

```text
<task>
Organisez les notes de réunion en compte-rendu, liste de tâches et points à vérifier lors de la prochaine réunion.
</task>
<context>
<pm_context>
[Collez ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Collez ici le contenu de MEETING_MINUTES_CONTEXT.md]
</specific_context>
</context>
<input>
【Informations sur la réunion (informations confidentielles masquées)】

### Objectif de la réunion
(Entrez)

### Type de réunion
(Entrez)

### Rôles des participants (sans les noms réels)
(Entrez)

### Notes de réunion et déclarations orales
(Entrez)

### Contenu pouvant ressembler à une décision
(Entrez)

### Points en attente
(Entrez)

### Contenu pouvant ressembler à une tâche
(Entrez)

### Points à vérifier lors de la prochaine réunion
(Entrez)
</input>
<constraints>
- Ne transmettez pas de noms réels de participants, de clients, de sociétés ou de personnes permettant une identification directe à l'IA.
- Les informations complémentaires manquantes doivent être indiquées « (supposition) ».
- Les confirmations de délais, de coûts ou de dépenses doivent être validées par un humain.
- Le compte-rendu destiné au client doit être vérifié et corrigé par un humain avant envoi.
</constraints>
<output_format>
1. Synthèse de la réunion
2. Liste des décisions prises
3. Liste des points en attente
4. Liste des tâches
5. Liste des tâches sans responsable assigné
6. Points à vérifier lors de la prochaine réunion
7. Risques et points de vigilance
</output_format>
```