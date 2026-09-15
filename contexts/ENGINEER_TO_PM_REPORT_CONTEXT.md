# Contexte de consultation d'ingénieur vers PM / Engineer to PM Report Context

---

## Purpose (objectif de ce contexte)

Ce contexte permet d'organiser, avec l'aide de l'IA, la communication d'un responsable technique / ingénieur vers le PM sur les problèmes techniques, les contraintes, l'impact, les options et la demande de décision.

**L'IA ne remplace pas la décision du PM.** L'IA aide à structurer et à créer des brouillons d'information. La décision finale doit toujours être prise par un humain.

> [!CAUTION]
> Ne transmettez pas de code source, d'informations d'authentification, de clés API, de mots de passe ou de spécifications techniques détaillées à l'IA.
> Ne transmettez pas de noms de clients, de sociétés, de personnes ou d'informations contractuelles à l'IA.
> Les informations techniques doivent être résumées sous forme de concepts, d'impact et de risques.

---

## Use Case (scénarios d'utilisation)

- Pour signaler un problème technique au PM
- Pour créer un brouillon de demande de décision au PM
- Pour présenter clairement des options techniques au PM
- Pour structurer l'impact des contraintes techniques sur les délais et la qualité
- Pour organiser les points à discuter avec le PM

---

## Input (informations à transmettre à l'IA)

Après avoir chargé ce contexte, transmettez (en masquant les informations confidentielles) :

```
### Problème technique / ce qui pose problème (du point de vue du concept et de l'impact ; ne pas inclure de code)
(ex. : un changement de spécification d'une API externe rend le flux de traitement existant inutilisable)

### Portée de l'impact
(Fonctionnalités, processus, délais, qualité concernées)

### Options
(Les options envisageables sous forme de liste)

### Ce sur quoi vous souhaitez que le PM décide
(Éléments sur lesquels vous demandez une décision au PM)

### Option recommandée et sa raison
(Recommandation du point de vue de l'ingénieur et sa justification)

### Contraintes techniques
(Aperçu des contraintes techniques, environnement, compétences)

### Impact sur les délais et la qualité
(Aperçu de l'impact de chaque option sur les délais et la qualité)
```

---

## Output (résultat attendu de l'IA)

### 1. Consultation au PM (brouillon)

Brouillon structuré permettant au PM de comprendre la situation et de décider.

### 2. Organisation des points de décision

Liste des points sur lesquels le PM doit prendre une décision.

### 3. Clarification de la demande de décision

Clarification de ce qui doit être décidé, dans quel délai et avec quel niveau de détail.

### 4. Comparaison des options

Tableau comparatif des options : résumé, avantages, inconvénients, risques.

### 5. Option recommandée et sa raison

Option recommandée du point de vue de l'ingénieur et sa justification.

### 6. Explication des risques

Organisation des risques liés au retard dans la décision ou au choix de chaque option.

### 7. Prochaines actions

Options d'actions après la décision du PM.

---

## Caution (précautions d'utilisation)

- **Ne transmettez pas de code source, d'informations d'authentification, de clés API, de mots de passe à l'IA.**
- Les informations techniques doivent être résumées sous forme de concepts, d'impact et de risques.
- Ne transmettez pas de noms de clients, de sociétés, de personnes ou d'informations contractuelles à l'IA.
- Le texte de consultation est un brouillon. Modifiez-le selon la situation réelle et la relation.
- Faites particulièrement attention aux éléments relatifs aux délais, aux coûts et aux responsabilités.
- **L'IA ne remplace pas la décision du PM ou de l'ingénieur.** La décision finale doit toujours être prise par un humain.

---

## Exemple d'utilisation (template)

```text
Basé sur ce contexte, veuillez structurer un problème technique à destination du PM.

## Contexte

[Collez ici le contenu de PM_CONTEXT.md]
[Collez ici le contenu de ENGINEER_TO_PM_REPORT_CONTEXT.md]

---

## Contenu de la consultation (informations confidentielles masquées ; ne pas inclure de code)

### Problème technique / ce qui pose problème
(Entrez)

### Portée de l'impact
(Entrez)

### Options
(Entrez)

### Ce sur quoi vous souhaitez que le PM décide
(Entrez)

### Option recommandée et sa raison
(Entrez)

### Contraintes techniques
(Entrez)

### Impact sur les délais et la qualité
(Entrez)

---

## Résultat attendu

1. Brouillon de consultation au PM
2. Organisation des points de décision
3. Clarification de la demande de décision (quoi, quand, niveau de détail)
4. Tableau comparatif des options
5. Option recommandée et sa justification
6. Explication des risques
7. Prochaines actions après la décision du PM

※ Ne transmettez pas de code source ou d'informations d'authentification à l'IA.
※ Le résultat est un brouillon ; la décision finale doit toujours être prise par un humain.
```

---

## Exemple d'utilisation pour Claude (version XML)

```text
<task>
Organisez le contenu de consultation technique à destination du PM.
</task>
<context>
<pm_context>
[Collez ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Collez ici le contenu de ENGINEER_TO_PM_REPORT_CONTEXT.md]
</specific_context>
</context>
<input>
【Contenu de la consultation (informations confidentielles masquées ; ne pas inclure de code)】

### Problème technique / ce qui pose problème
(Entrez)

### Portée de l'impact
(Entrez)

### Options
(Entrez)

### Ce sur quoi vous souhaitez que le PM décide
(Entrez)

### Option recommandée et sa raison
(Entrez)

### Contraintes techniques
(Entrez)

### Impact sur les délais et la qualité
(Entrez)
</input>
<constraints>
- Ne transmettez pas de code source, d'informations d'authentification, de noms de clients, de sociétés, de personnes ou d'informations contractuelles.
- Les informations techniques doivent être résumées sous forme de concepts, d'impact et de risques.
- Si des informations manquent, indiquez « (supposition) ». Prenez des décisions avec des informations insuffisantes uniquement si cela est nécessaire.
- La décision finale de conception doit être prise par l'ingénieur et le PM.
</constraints>
<output_format>
1. Brouillon de consultation au PM
2. Organisation des points de décision
3. Clarification de la demande de décision
4. Tableau comparatif des options
5. Option recommandée et sa justification
6. Explication des risques
7. Prochaines actions
</output_format>
```
