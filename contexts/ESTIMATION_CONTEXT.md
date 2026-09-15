# Contexte d'organisation des estimations / Estimation Context

---

## Purpose (objectif de ce contexte)

Avant de fournir un devis, ce contexte permet d'organiser les notes de exigences, les hypothèses, les points inconnus, les contraintes, la portée non incluse et l'incertitude. Il aide à vérifier les conditions préalables et à organiser la demande de confirmation au client.

**L'IA ne remplace pas la décision du PM.** ** Ne demandez pas à l'IA de calculer ou de valider des montants ou des conditions contractuelles. ** L'IA ne sert qu'à organiser les conditions préalables et à lister les éléments à vérifier.

> [!CAUTION]
> Ne transmettez pas de montants, de conditions contractuelles, d'informations d'authentification ou de détails précis d'études réelles à l'IA.
> Ne transmettez pas de noms de clients, de sociétés ou de personnes.
> Les décisions finales concernant le devis, les coûts et les contrats doivent toujours être prises par un humain.

---

## Use Case (scénarios d'utilisation)

- Organiser les conditions préalables et les points inconnus avant de commencer le devis
- Identifier les incertitudes et les risques à partir des notes de exigences
- Organiser les éléments à exclure de la portée du devis
- Organiser les conditions qui entraîneraient un devis supplémentaire
- Créer une liste de questions à poser au client

---

## Input (informations à transmettre à l'IA)

Après avoir chargé ce contexte, transmettez (en masquant les informations confidentielles et les données personnelles) :

```
### Notes de exigences / résumé des demandes du client
(Notes sur les fonctions / exigences. Ne pas inclure de code source ou d'informations d'authentification)

### Conditions préalables confirmées
(Listez les éléments que vous considérez comme étant des conditions préalables)

### Points inconnus / non confirmés
(Éléments non confirmés concernant les exigences, les spécifications, l'environnement, l'équipe, etc.)

### Contraintes
(Délais, ressources disponibles, pile technologique, budget estimatif, etc.)

### Scope non souhaité
(Éléments à envelopper ou non dans la portée du projet)

### Études similaires / informations de référence (informations abstraites uniquement)
(Tendances / estimées d'études similaires, sans informations spécifiques)

### Contraintes de délais / ressources
(Délais estimés, résumé des ressources disponibles)
```

---

## Output (résultat attendu de l'IA)

### 1. Synthèse des conditions préalables du devis

Regrouper les conditions préalables actuelles du devis.

### 2. Organisation des incertitudes et des risques

Liste des éléments d'incertitude et de risque pouvant impacter le devis.

### 3. Liste des questions à poser au client

Liste des questions à confirmer avec le client.

### 4. Organisation de la portée non incluse

Organisation des éléments à exclure ou non de la portée du devis, avec justification.

### 5. Conditions entraînant un devis supplémentaire

Conditions qui nécessiteraient un devis supplémentaire si elles devaient être ajoutées.

### 6. Notes pour la réflexion incluant le risque

Notes pour la réflexion sur les incertitudes et les risques (ne demandez pas à l'IA de calculer un montant).

### 7. Synthèse des éléments à confirmer avec le client avant l'envoi du devis

Liste des éléments à confirmer avec le client avant l'envoi du devis.

---

## Caution (précautions d'utilisation)

- **Ne demandez pas à l'IA de calculer ou de valider des montants ou des conditions contractuelles. ** L'IA ne sert qu'à organiser les conditions préalables et à vérifier les éléments.
- Ne transmettez pas les contenus devisés, contractuels ou des projets réels à l'IA.
- Ne transmettez pas de noms de clients, de sociétés ou de personnes ou d'informations d'authentification.
- Vérifiez toujours les éléments de sortie de l'IA contre la réalité.
- **L'IA ne remplace pas la décision du PM.** La décision finale doit toujours être prise par un humain.

---

## Exemple d'utilisation (template)

```text
Basé sur ce contexte, organisez les conditions préalables du devis et les points à vérifier.

## Contexte

[Collez ici le contenu de PM_CONTEXT.md]
[Collez ici le contenu d'ESTIMATION_CONTEXT.md]

---

## Informations préalables (informations confidentielles masquées)

### Notes de exigences / résumé des demandes du client
(Entrez)

### Conditions préalables confirmées
(Entrez)

### Points inconnus / non confirmés
(Entrez)

### Contraintes
(Entrez)

### Scope non souhaité
(Entrez)

### Études similaires / informations de référence (informations abstraites uniquement)
(Entrez)

### Contraintes de délais / ressources
(Entrez)

---

## Résultat attendu

1. Synthèse des conditions préalables du devis
2. Organisation des incertitudes et des risques
3. Questions à poser au client
4. Organisation de la portée non incluse
5. Conditions entraînant un devis supplémentaire
6. Notes de réflexion incluant le risque
7. Éléments à confirmer avec le client avant l'envoi du devis

※ Ne demandez pas à l'IA de calculer ou de valider des montants ou des conditions contractuelles.
※ La décision finale du devis doit toujours être prise par un humain.
```

---

### Exemple: identification des incertitudes impactant le devis

```text
Basé sur ce contexte, identifiez les incertitudes impactant le devis.

## Contexte

[Collez ici le contenu de PM_CONTEXT.md]
[Collez ici le contenu d'ESTIMATION_CONTEXT.md]

---

## Informations sur le projet (informations confidentielles masquées)

### Notes de exigences / résumé des demandes du client
(Entrez)

### Incertitudes actuelles
(Entrez)

### Études similaires / informations de référence (informations abstraites uniquement)
(Entrez)

---

## Résultat attendu

1. Incertitudes impactant le devis (probabilité d'impact, gravité)
2. Éléments pour lesquels il vaut mieux attendre d'avoir une confirmation avant de commencer le devis
3. Risques si un devis est établi sur des hypothèses
4. Priorité de vérification des incertitudes

※ La décision finale du devis doit toujours être prise par un humain.
※ Ne transmettez pas d'informations confidentielles ou d'informations d'authentification.
```

---

### Exemple: organisation de la portée non incluse

```text
Basé sur ce contexte, organisez les éléments à exclure de la portée du devis.

## Contexte

[Collez ici le contenu de PM_CONTEXT.md]
[Collez ici le contenu d'ESTIMATION_CONTEXT.md]

---

## Informations sur la portée (informations confidentielles masquées)

### Notes de exigences / résumé des demandes du client
(Entrez)

### Éléments à ne pas inclure dans le devis
(Entrez)

### Elements flous des demandes du client
(Entrez)

---

## Résultat attendu

1. Organisation des éléments à exclure (avec justification)
2. Impacts potentiels sur le client si ces éléments sont exclus
3. Questions à poser au client avant de finaliser la portée
4. Conditions entraînant un devis supplémentaire

※ La décision finale du devis doit toujours être prise par un humain.
※ Ne transmettez pas d'informations confidentielles ou d'informations d'authentification.
```

---

## Exemple d'utilisation pour Claude (version XML)

```text
<task>
Organisez les conditions préalables du devis, les incertitudes, les questions à poser au client et les éléments à exclure de la portée.
</task>
<context>
<pm_context>
[Collez ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Collez ici le contenu d'ESTIMATION_CONTEXT.md]
</specific_context>
</context>
<input>
【Informations préalables (informations confidentielles masquées)】

### Notes de exigences / résumé des demandes du client
(Entrez)

### Conditions préalables confirmées
(Entrez)

### Points inconnus / non confirmés
(Entrez)

### Contraintes
(Entrez)

### Scope non souhaité
(Entrez)
</input>
<constraints>
- Ne transmettez pas de noms de clients, de personnes, de sociétés, d'informations contractuelles ou d'informations d'authentification.
- Ne calculez ou ne validez pas de montants ou de conditions contractuelles.
- Si des informations manquent, indiquez « (supposition) ». 
- La décision finale du devis doit être prise par un humain.
</constraints>
<output_format>
1. Synthèse des conditions préalables
2. Incertitudes et risques
3. Questions à poser au client
4. Portée non incluse
5. Conditions entraînant un frais supplémentaire
</output_format>
```
