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

Texte concis expliquant la situation.

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
> Ne transmettez pas d'informations confidentielles, de données personnelles, d'informations de contrat ou d'informations d'authentification à l'IA.

---

## Exemple d'utilisation (template)

### 【Modèle de base】Créer un brouillon de texte client

```text
# Demande de rédaction d'un texte client

En vous appuyant sur les contextes ci-dessous, veuillez créer un brouillon de texte destiné au client.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]

[Coller ici le contenu de CLIENT_COMMUNICATION_CONTEXT.md]

---

## Objet de la demande (informations confidentielles masquées)

### Ce que vous souhaitez transmettre au client
-

### Contexte / historique
-

### Situation actuelle
-

### Votre point de vue
-

### Ce que vous souhaitez consulter / confirmer au client
-

### Options à présenter (le cas échéant)
-

### Expressions / ton à éviter
-

### Relation avec le client
-

---

## Livrables attendus

1. Brouillon d'email au client (objet, corps, conclusion)
2. Texte d'explication de la situation
3. Texte de présentation des options (le cas échéant)
4. Mémo d'explication avant la réunion

---

## Précautions

※ La sortie de l'IA est un brouillon. Ne l'envoyez pas tel quel au client.
※ Les expressions relatives au contrat, aux délais, aux coûts et au périmètre de responsabilité doivent impérativement être vérifiées par un humain.
※ La transmission finale doit être validée par le responsable / la hiérarchie.
```

---

### 【Confirmation des spécifications】Brouillon d'email pour confirmer les spécifications avec le client

```text
En vous appuyant sur les contextes ci-dessous, veuillez créer un brouillon d'email de confirmation des spécifications.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de CLIENT_COMMUNICATION_CONTEXT.md]

---

## Contenu de la demande (informations confidentielles masquées)

### Spécifications / exigences à confirmer
-

### Contexte / raison justifiant la confirmation
-

### Travaux impactés si absence de confirmation
-

### Délai de réponse souhaité (le cas échéant)
-

---

## Livrables attendus

1. Proposition d'objet
2. Corps (confirmation structurée sous forme de liste)
3. Ton : courtois, coopératif, posture de demande de confirmation

※ N'incluez aucune expression qui engage la responsabilité ou confirme des délais.
※ La sortie de l'IA est un brouillon. Ne l'envoyez pas tel quel.
※ N'envoyez pas d'informations confidentielles ou personnelles à l'IA.
```

---

### 【Consultation sur le retard】Brouillon d'email pour consulter / expliquer le retard au client

```text
En vous appuyant sur les contextes ci-dessous, veuillez créer un brouillon d'email pour consulter le client au sujet du retard.
Adoptez un ton de consultation sur l'explication de la situation et la politique de réponse, plutôt qu'une excuse unilatérale.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de CLIENT_COMMUNICATION_CONTEXT.md]

---

## Situation du retard (informations confidentielles masquées)

### Travaux / jalons en retard
-

### Durée / période de retard estimée
-

### Cause du retard (dans la limite de ce qui peut être expliqué au client)
-

### Impact sur le client
-

### Politique de réponse / plan de récupération de notre côté
-

### Éléments à consulter / confirmer auprès du client
-

---

## Livrables attendus

1. Proposition d'objet
2. Corps (faits du retard, impacts, politique de réponse, consultation du client)
3. Le cas échéant, organisation des options à présenter

※ N'incluez aucune expression engageant la responsabilité, la compensation ou les dommages.
※ Les expressions confirmant des délais doivent être vérifiées par un humain avant rédaction.
※ La sortie de l'IA est un brouillon. Validez auprès de votre hiérarchie avant envoi.
```

---

## Exemple d'utilisation pour Claude (version XML)

Lors d'un échange avec Claude, la structure à balises XML suivante permet de distinguer clairement la demande, les informations d'entrée et les contraintes.

```text
<task>
À partir de la situation ci-dessous, créez un brouillon de texte destiné au client (email, texte d'explication, texte de consultation).
Restituez la situation, le texte client et les remarques / points de vigilance.
</task>
<context>
<pm_context>
[Coller ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Coller ici le contenu de CLIENT_COMMUNICATION_CONTEXT.md]
</specific_context>
</context>
<input>
【Objet de la demande (informations confidentielles masquées)】

### Ce que vous souhaitez transmettre au client
-

### Contexte / historique
-

### Situation actuelle
-

### Votre point de vue
-

### Ce que vous souhaitez consulter / confirmer au client
-

### Options à présenter (le cas échéant)
-

### Expressions / ton à éviter
-

### Relation avec le client
-
</input>
<constraints>
- Considérez que les noms de clients, de personnes, de sociétés, les informations contractuelles et les informations d'authentification sont masqués.
- N'affirmez aucune expression relative au contrat, aux délais, aux coûts, au périmètre de responsabilité ou à la compensation.
- N'affirmez pas qu'un point est « juridiquement sans problème » ou « contractuellement sans problème ».
- La sortie de l'IA est un élément d'aide à la décision ; la transmission finale doit être vérifiée et corrigée par un humain.
</constraints>
<output_format>
1. Organisation de la situation (contexte, impact client, points à trancher)
2. Brouillon d'email au client (objet, corps, conclusion)
3. Texte de présentation des options (le cas échéant)
4. Remarques / points de vigilance (éléments devant être vérifiés par un humain)
</output_format>
```
