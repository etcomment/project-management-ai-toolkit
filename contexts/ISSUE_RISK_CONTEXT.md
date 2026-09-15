# Contexte de gestion des problèmes et risques / Issue & Risk Management Context

---

## Purpose (objectif de ce contexte)

Pour aider le PM à vérifier s'il manque des éléments, classer, réviser la priorité et identifier des candidats à l'escalade dans la liste des problèmes et des risques d'un projet, en fournissant ces informations à l'IA.

**L'IA ne prend pas les décisions d'évaluation des risques ni les décisions de priorité opérationnelle.** Les résultats sont uniquement un support d'organisation et de classification. La décision finale doit toujours être prise par un humain.

> [!CAUTION]
> Ne transmettez pas d'informations personnelles, d'informations contractuelles, d'informations d'authentification ou de détails spécifiques de projets réels à l'IA.
> Ne transmettez pas d'informations sur l'évaluation individuelle des personnes.
> Les évaluations de risques, les décisions de priorité et les décisions d'escalade doivent être confirmées par un humain.

---

## Use Case (scénarios d'utilisation)

- Vérifier s'il manque des éléments dans la liste des problèmes
- Réviser la priorité des problèmes et des risques
- Identifier les problèmes sans responsable assigné ou sans date limite claire
- Identifier les candidats à l'escalade
- Organiser les problèmes et risques nécessitant une confirmation du client

---

## Input (informations à transmettre à l'IA)

Après avoir chargé ce contexte, transmettez (en masquant les informations confidentielles et les données personnelles) :

```
### Liste des problèmes

| No. | Contenu du problème / problème | Statut | Responsable (rôle) | Date limite | Portée de l'impact | Politique de réponse |
|---|---|---|---|---|---|---|
| 1 | | | | | | |
| 2 | | | | | | |
| 3 | | | | | | |

### Questions non résolues (éléments que personne n'a traités)
-

### Dépendances externes (attente de confirmation du client, du fournisseur externe, de l'API externe, etc.)
-

### Questions nécessitant une confirmation du client
-

### Liste des risques (risques qui pourraient se manifester mais qui ne sont pas encore devenus des problèmes)

| No. | Contenu du risque | Probabilité (élevée / moyenne / faible) | Impact (élevé / moyen / faible) | Politique de réponse |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |
```

---

## Output (résultat attendu de l'IA)

### 1. Classification des problèmes

Classifiez selon les critères suivants :

- Nécessite une réponse immédiate (impact élevé, urgence élevée)
- Attention nécessaire (impact moyen, urgence moyenne)
- Gestion continue (impact faible, urgence faible)
- Décision impossible (informations insuffisantes)

### 2. Révision de la priorité

Identifiez si la priorité actuelle est appropriée, du point de vue du PM.

### 3. Problèmes sans responsable assigné

Liste des problèmes dont le responsable n'est pas défini ou est peu clair.

### 4. Problèmes sans date limite clairs

Liste des problèmes dont la date limite n'est pas définie ou est peu claire.

### 5. Problèmes à impact ambigu

Liste des problèmes dont la portée de l'impact est « inconnue », « non confirmée » ou « TBD ».

### 6. Risques potentiels

Indiquez les risques que le PM pourrait avoir manqués, sur la base des informations fournies.

### 7. Candidats à l'escalade

Liste des problèmes / risques correspondant à l'une des conditions suivantes :

- Problème important qui ne peut pas être résolu par le PM seul
- Peut avoir un impact majeur sur le délai, la qualité ou la relation avec le client
- Problème de ressources ou d'organisation interne nécessitant une décision du supérieur

### 8. Prochaines actions

Liste des actions à entreprendre dans un avenir immédiat.

---

## Format de sortie (modèle de tableau)

Vous pouvez spécifier le format de sortie suivant pour l'IA :

```text
Veuillez produire le résultat dans le format suivant.

## Résumé de l'organisation des problèmes

| Classification | Nombre | Contenu principal |
|---|---|---|
| Nécessite une réponse immédiate | | |
| Attention nécessaire | | |
| Gestion continue | | |
| Sans responsable | | |
| Sans date limite | | |

## Candidats à l'escalade

| No. | Contenu | Raison | Réponse recommandée |
|---|---|---|---|
| | | | |

## Liste des prochaines actions

| Priorité | Action | Responsable (rôle) | Date limite |
|---|---|---|---|
| | | | |
```

---

## Caution (précautions d'utilisation)

> [!CAUTION]
> L'organisation des problèmes et des risques par l'IA ne remplace pas une évaluation des risques par des experts, un audit ou un diagnostic.
>
> Les décisions finales concernant la priorité, l'escalade et le traitement doivent toujours être prises par un humain.
>
> Ne transmettez pas d'informations personnelles, d'informations contractuelles, d'informations d'authentification ou de détails spécifiques de projets réels à l'IA.

---

## Exemple d'utilisation (template)

```text
# Demande de revue des problèmes et risques

Sur la base de ce contexte, veuillez revoir les problèmes et risques du point de vue du PM.

## Contexte

[Collez ici le contenu de PM_CONTEXT.md]

[Collez ici le contenu d'ISSUE_RISK_CONTEXT.md]

---

## Informations sur les problèmes et risques (informations confidentielles masquées)

### Liste des problèmes

| No. | Contenu du problème | Statut | Responsable (rôle) | Date limite | Portée de l'impact |
|---|---|---|---|---|---|
| 1 | | | | | |

### Questions non résolues
-

### Dépendances externes
-

### Questions nécessitant une confirmation du client
-

### Liste des risques

| No. | Contenu du risque | Probabilité | Impact | Politique de réponse |
|---|---|---|---|---|
| 1 | | | | |

---

## Résultat attendu

1. Classification des problèmes (y compris les problèmes sans responsable / sans date limite / à impact ambigu)
2. Révision de la priorité
3. Problèmes sans responsable / sans date limite / à impact ambigu
4. Risques potentiels
5. Candidats à l'escalade et raison
6. Liste des prochaines actions (priorité, responsable, date limite)

※ Le résultat de l'IA est un support de décision. La décision finale doit toujours être prise par un humain.
```

---

## Exemple d'utilisation pour Claude (version XML)

```text
<task>
Revoyez les problèmes et risques du point de vue du PM. Identifiez les problèmes sans responsable / sans date limite / à impact ambigu, les risques potentiels, les candidats à l'escalade et les prochaines actions.
</task>
<context>
<pm_context>
[Collez ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Collez ici le contenu d'ISSUE_RISK_CONTEXT.md]
</specific_context>
</context>
<input>
【Informations sur les problèmes et risques (informations confidentielles masquées)】

### Liste des problèmes

| No. | Contenu du problème | Statut | Responsable (rôle) | Date limite | Portée de l'impact |
|---|---|---|---|---|---|
| 1 | | | | | |

### Questions non résolues
-

### Dépendances externes
-

### Questions nécessitant une confirmation du client
-

### Liste des risques

| No. | Contenu du risque | Probabilité | Impact | Politique de réponse |
|---|---|---|---|---|
| 1 | | | | |
</input>
<constraints>
- Ne transmettez pas de noms de clients, de personnes, de sociétés, d'informations contractuelles ou d'informations d'authentification.
- Les évaluations de risques et les décisions de priorité doivent être confirmées par un humain.
- Si des informations manquent, indiquez « (supposition) ». 
- L'IA est un support de décision. La décision finale doit toujours être prise par un humain.
</constraints>
<output_format>
1. Classification des problèmes
2. Révision de la priorité
3. Problèmes sans responsable / sans date limite / à impact ambigu
4. Risques potentiels
5. Candidats à l'escalade et raison
6. Liste des prochaines actions
</output_format>
```
