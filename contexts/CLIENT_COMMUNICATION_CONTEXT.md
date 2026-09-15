# Contexte de communication client / Client Communication Context

---

## Purpose (objectif de ce contexte)

Contexte pour créer, avec l'aide de l'IA, des brouillons de communication client : explications, emails, rapports.

Objectif : structurer la situation, la consultation, l'explication du retard, la présentation des options, etc.

**L'IA ne remplace pas la décision du PM.** L'IA aide à organiser et à lister des options de récupération. La décision finale doit toujours être prise par un humain.

> [!CAUTION]
> Ne transmettez pas directement au client les textes de l'IA. Vérifiez toujours les expressions relatives au contrat, aux délais, aux coûts et aux responsabilités.

---

## Use Case (scénarios d'utilisation)

- Rédiger un email d'explication de la situation au client
- Consulter / signaler un retard ou un problème au client
- Présenter des options au client
- Organiser les points d'explication avant une réunion
- Réfléchir au ton et à l'expression de la communication

---

## Input (informations à transmettre à l'IA)

Après avoir chargé ce contexte, transmettez (en masquant les informations confidentielles) :

```
### Ce que vous souhaitez transmettre au client
-

### Contexte / historique (pourquoi cette communication est nécessaire)
-

### Situation actuelle
-

### Votre point de vue / position
-

### Ce que vous souhaitez consulter / confirmer au client
-

### Options à présenter (le cas échéant)
- Option A :
- Option B :
- Option C (facultatif) :

### Expressions / ton à éviter
- (ex. : expressions qui affirment la responsabilité)
- (ex. : expressions de désolé excessives)
- (ex. : expressions qui blâment le client)

### Relation / situation avec le client
- Degré de tension : (ex. : normal / légèrement tendu / critique)
- Historique de communication : (ex. : abordé lors de la réunion régulière de la semaine dernière)
- Situation du contact client (par rôle) :
```

---

## Output (résultat attendu de l'IA)

### 1. Brouillon d'email au client

Brouillon d'email client incluant objet, corps et conclusion.

### 2. Texte d'explication de la situation

Texte concise expliquant la situation.

### 3. Texte de consultation

Texte proposant des options au client.

### 4. Texte d'explication du retard

Texte expliquant la situation du retard, l'impact, la politique de réponse et l'impact sur le client.

### 5. Texte de présentation des options

Texte présentant plusieurs options de réponse au client.

### 6. Mémo d'explication avant la réunion

Mémo structurant les points à transmettre lors de la réunion.

---

## Caution (précautions d'utilisation)

> [!CAUTION]
> **Le texte client généré par l'IA ne doit pas être envoyé directement au client.**
>
> Vérifiez particulièrement les expressions relatives aux éléments suivants :
> - Expressions relatives au contrat, au bon de commande, aux coûts
> - Confirmations de délais et d'horaires
> - Expressions relatives à la responsabilité, à la compensation, aux dommages
> - Expressions relatives aux normes de qualité et aux critères d'acceptation
>
> Ces éléments doivent toujours être confirmés et corrigés par un humain, adaptés à la situation du cas, aux conditions du contrat et à la politique interne.
>
> Ne transmettez pas d'informations confidentielles, de données personnelles, de informations de contrat ou d'informations d'authentification à l'IA.
