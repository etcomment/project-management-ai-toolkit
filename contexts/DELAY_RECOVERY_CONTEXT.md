# Contexte de gestion des retards / Contexte de reprise après délai

---

## Purpose (objectif de ce contexte)

Ce contexte permet de structurer la situation, les impacts, les mesures de récupération, la hiérarchisation et les explications aux clients lorsqu'un retard se produit. Il aide à organiser l'intervention initiale et à examiner les politiques de réponse.

**L'IA ne remplace pas la décision du PM.** L'IA est un outil pour organiser et lister les options de récupération. La décision finale doit toujours être prise par un humain.

> [!CAUTION]
> Ne transmettez pas d'informations confidentielles, de données personnelles, de données contractuelles ou d'informations d'authentification à l'IA.
> Les expressions relatives aux délais et aux coûts doivent être confirmées par un humain avant utilisation.

---

## Use Case (scénarios d'utilisation)

- Organiser la situation lorsqu'un retard se produit ou devient évident
- Lister les options de récupération lorsqu'un retard se produit
- Créer un brouillon d'explication de retard au client
- Structurer un matériel d'escalade interne
- Planifier une intervention dans les 72 heures suivantes

---

## Input (informations à transmettre à l'IA)

Après avoir chargé ce contexte, transmettez (en masquant les informations confidentielles et les données personnelles) :

```
### Travaux retardés
(Listez les travaux, fonctionnalités ou étapes en retard)

### Raison du retard
(Listez les raisons possibles du retard)

### Délai de retard / ampleur
(Combien de jours ou de semaines de retard, ou ampleur de l'impact)

### Travaux restants
(Listez les travaux restants)

### Chemin critique
(Flux de travaux directement impactant les délais)

### Ressources disponibles
(Personnes disponibles, ressources externes disponibles, etc.)

### Délais / contraintes inchangés
(Dates / contraintes contractuelles qui ne peuvent pas être modifiées)

### Impact sur le client
(Impact du retard sur le client, les utilisateurs)

### Actions déjà entreprises
(Tout ce qui a déjà été fait pour faire face au retard)
```

---

## Output (résultat attendu de l'IA)

### 1. Analyse des causes de retard

Classification et organisation des causes directes et des facteurs contextuels.

### 2. Analyse d'impact

Portée de l'impact sur les travaux, les fonctionnalités, les relations.

### 3. Options de récupération

Plusieurs solutions de récupération et leurs compromis respectifs.

### 4. Hiérarchisation des travaux restants

Ordre de priorité pour les travaux restants.

### 5. Travaux potentiellement supprimés

Travaux potentiellement supprimés en cas de réévaluation de la qualité et des délais.

### 6. Travaux nécessitant une assistance supplémentaire

Travaux nécessitant des ressources externes ou l'aide d'un senior.

### 7. Explications de retard au client (brouillon)

Brouillon d'explication de la situation de retard au client.

### 8. Plan d'escalade interne (brouillon)

Brouillon de plan d'escalade pour les seniors, les chefs de projet, etc.

### 9. Actions à entreprendre dans les 24 à 72 heures

Liste des actions immédiates et prioritaires.

---

## Caution (précautions d'utilisation)

- **Les réponses relatives aux délais, aux coûts et aux responsabilités doivent être confirmées par un humain et ne pas être utilisées telles quelles.**
- **Le texte d'explication du retard au client est un brouillon ; la confirmation finale doit être validée par un humain avant envoi.**
- **Ne transmettez pas d'informations personnellement identifiables, de données confidentielles, de données contractuelles ou d'informations d'authentification à l'IA.**
- **Les décisions finales concernant la situation doivent toujours être prises par un humain.**

---

## Exemple d'utilisation (template)

Copiez le modèle ci-dessous, complétez-le avec les informations du projet, puis utilisez-le.

```text
En vous appuyant sur les contextes ci-dessous, veuillez examiner la situation de retard et définir une politique de récupération.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de DELAY_RECOVERY_CONTEXT.md]

---

## Situation du retard (informations confidentielles masquées)

### Travaux retardés
(Listez les travaux, fonctionnalités ou étapes en retard)

### Raison du retard
(Listez les raisons possibles du retard)

### Délai de retard / ampleur
(Indiquez le nombre de jours / de semaines de retard et l'ampleur de l'impact)

### Travaux restants
(Listez les travaux restants)

### Chemin critique
(Flux de travaux directement impactant les délais)

### Ressources disponibles
(Personnes disponibles, ressources externes disponibles, etc.)

### Délais / contraintes inchangés
(Dates / contraintes contractuelles qui ne peuvent pas être modifiées)

### Impact sur le client
(Impact du retard sur le client, les utilisateurs)

### Actions déjà entreprises
(Tout ce qui a déjà été fait pour faire face au retard)

---

## Livrables attendus

1. Organisation des causes de retard (causes directes, facteurs contextuels)
2. Périmètre d'impact
3. Options de récupération (plusieurs options, avec arbitrages / trade-offs)
4. Proposition de priorisation des travaux restants
5. Identification des travaux potentiellement supprimables
6. Identification des travaux nécessitant une assistance supplémentaire
7. Ossature de l'explication de retard au client
8. Ossature du plan d'escalade interne
9. Actions à entreprendre dans les 24 à 72 prochaines heures

※ Toute décision relative aux délais, aux coûts et au périmètre de responsabilité doit être prise par un humain.
※ La sortie de l'IA est un brouillon de synthèse. Vérifiez impérativement par un humain avant toute communication au client.
```

---

## Exemple d'utilisation pour Claude (version XML)

Lors d'un échange avec Claude, la structure à balises XML suivante permet de distinguer clairement la demande, les informations d'entrée et les contraintes.

```text
<task>
Sur la base de la situation de retard ci-dessous, organisez les causes du retard, le périmètre d'impact, les options de récupération, les priorités et la politique d'explication au client.
</task>
<context>
<pm_context>
[Coller ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Coller ici le contenu de DELAY_RECOVERY_CONTEXT.md]
</specific_context>
</context>
<input>
【Situation du retard (informations confidentielles masquées)】

### Travaux retardés
(Entrez)

### Raison du retard
(Entrez)

### Délai de retard / ampleur
(Entrez)

### Travaux restants
(Entrez)

### Délais / contraintes inchangés
(Entrez)

### Impact sur le client
(Entrez)

### Actions déjà entreprises
(Entrez)
</input>
<constraints>
- Considérez que les noms de clients, de personnes, de sociétés, les informations contractuelles et les informations d'authentification sont masqués.
- Tout élément complété en dehors des informations d'entrée doit être signalé comme « (Hypothèse) ».
- N'incluez aucune expression qui confirme des délais, des coûts ou le périmètre de responsabilité.
- Précisez que le brouillon d'explication au client doit être validé par la hiérarchie / les parties concernées.
- La sortie de l'IA est un élément d'aide à la décision ; la décision finale revient à un humain.
</constraints>
<output_format>
1. Organisation des causes de retard (causes directes, facteurs contextuels)
2. Périmètre d'impact
3. Options de récupération (plusieurs options, avec arbitrages / trade-offs)
4. Proposition de priorisation des travaux restants
5. Ossature de l'explication de retard au client (brouillon)
6. Ossature du plan d'escalade interne
7. Actions à entreprendre dans les 24 à 72 prochaines heures
</output_format>
```
