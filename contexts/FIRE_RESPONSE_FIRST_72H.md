# Contexte de réponse initiale aux incidents — 72 heures / Fire Response - First 72 Hours Context

---

## Purpose (objectif de ce contexte)

Ce contexte permet d'organiser les faits, les impacts et la stratégie de réponse lors des **72 premières heures** suivant la survenue d'un incident ou d'une crise dans un projet.

Lors des premières heures, qui peuvent facilement provoquer de la panique, l'IA aide à structurer les informations afin de clarifier **par quoi commencer**.

**Il faut d'abord organiser les faits, les impacts, les options et les prochaines actions, avant de rechercher les causes.**

**L'IA ne prend pas les décisions de gestion de crise.** Les résultats sont uniquement un support d'organisation et de classification. La décision finale doit toujours être prise par un humain.

---

## Use Case (scénarios d'utilisation)

- Lorsqu'un incident sur environnement de production ou un bug majeur survient
- Lorsqu'un client formule une réclamation ou un retour d'expérience grave
- Lorsqu'un dépassement de délai ou un retard important est certain
- Lorsqu'un problème majeur menace la poursuite du projet
- Lorsqu'une crise d'équipe survient ou qu'un membre clé quitte le projet

---

## Input (informations à transmettre à l'IA)

Après avoir chargé ce contexte, transmettez les informations suivantes (en masquant les données confidentielles).

**Indiquez « inconnu » pour les informations non disponibles.**

```
### Ce qui s'est produit (résumé de l'incident)
-

### Quand l'incident est-il survenu ?
- Date et heure de l'incident (ou de sa découverte) :
- Nombre d'heures écoulées depuis le début :

### Personnes concernées (indiquez les rôles, sans les noms propres ni le nom des sociétés)
- Côté client :
- Côté interne :
- Côté externe (fournisseur, partenaire, etc.) :

### Impact sur le client
- Utilisateurs / clients affectés (indiquez le rôle et l'ampleur) :
- Impact opérationnel (arrêt du système, problème de données, retard, etc.) :
- Situation actuelle du client (déjà contacté, non contacté, mécontent, etc.) :

### Impact sur l'organisation interne
- Impact sur l'équipe :
- Impact sur les autres projets / dossiers :
- Niveau actuel de notification auprès des supérieurs et de la direction :

### Faits actuellement confirmés
-

### Informations encore inconnues
-

### Réponses déjà engagées
-

### Délais et contraintes
- Délai de réponse du client :
- Délai de notification interne :
- Délais légaux ou contractuels (le cas échéant) :
```

---

## Output (résultat attendu de l'IA)

### 1. Séparation des faits et des hypothèses

Classement des informations fournies entre « faits confirmés » et « hypothèses / informations non confirmées ».

### 2. Organisation de l'impact

Liste des impacts sur le client, l'organisation interne et les parties externes.

### 3. Points à vérifier aujourd'hui

Liste priorisée des éléments à vérifier et à décider **aujourd'hui (dans les 24 heures)**.

### 4. Informations à transmettre au client

Éléments à inclure dans l'explication initiale ou le compte rendu au client.

(La formulation finale doit toujours être validée par un humain.)

### 5. Décisions à prendre en interne

Liste des décisions à prendre en interne par le PM, le responsable hiérarchique ou la direction.

### 6. Liste des actions de réponse initiale

Check-list des actions à engager immédiatement.

### 7. Plan de réponse sur 72 heures

Proposition de planning chronologique des actions à mener dans les 72 heures.

### 8. Nécessité d'une escalade

Éléments permettant d'apprécier la nécessité d'une escalade selon les critères suivants :

- Faut-il informer le responsable hiérarchique ou le PMO ?
- Faut-il informer la direction ?
- Faut-il demander un avis juridique ?
- Faut-il informer les interlocuteurs de haut niveau chez le client ?

---

## Caution (précautions d'utilisation)

> [!CAUTION]
> L'organisation de la réponse à la crise produite par l'IA ne remplace pas l'avis d'un spécialiste de la gestion de crise ou d'un juriste.
>
> **Les explications, excuses ou propositions d'indemnisation destinées au client ne doivent pas être utilisées telles quelles : elles doivent être vérifiées par le responsable hiérarchique, le service juridique ou le responsable du dossier.**
>
> Ne transmettez pas à l'IA de données confidentielles, de données personnelles, d'informations contractuelles ou d'informations d'authentification.
>
> Ne transmettez pas à l'IA les journaux de l'environnement de production, les détails des erreurs, le code source ou les informations d'authentification.

---

## Exemple d'utilisation

```text
# Demande d'organisation de la réponse initiale à un incident

Sur la base de ce contexte, organisez la situation actuelle de l'incident.
Il faut privilégier l'organisation des faits, des impacts, des options et des prochaines actions plutôt que la recherche de la cause.

## Contexte

[Collez ici le contenu de PM_CONTEXT.md]

[Collez ici le contenu de FIRE_RESPONSE_FIRST_72H.md]

---

## Situation actuelle (informations confidentielles masquées)

### Ce qui s'est produit
-

### Quand l'incident est-il survenu ?
-

### Impact sur le client
-

### Impact sur l'organisation interne
-

### Faits actuellement confirmés
-

### Informations encore inconnues
-

### Réponses déjà engagées
-

### Délais et contraintes
-

---

## Résultat attendu

1. Séparation des faits et des hypothèses
2. Organisation de l'impact
3. Points à vérifier aujourd'hui (dans les 24 heures)
4. Éléments à transmettre au client
5. Décisions à prendre en interne
6. Actions de réponse initiale
7. Plan de réponse sur 72 heures
8. Nécessité d'une escalade et recommandation

※ Le résultat de l'IA est un support de décision. La décision finale doit toujours être prise par un humain.
※ Les explications et excuses destinées au client doivent être vérifiées par le responsable hiérarchique et le service juridique.
```

---

## Exemple d'utilisation pour Claude (version XML)

```text
<task>
Organisez la réponse initiale sur 72 heures à cette situation d'incident.
Il faut privilégier l'organisation des faits, des impacts, des informations non confirmées et des actions initiales plutôt que la recherche de la cause.
</task>
<context>
<pm_context>
[Collez ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Collez ici le contenu de FIRE_RESPONSE_FIRST_72H.md]
</specific_context>
</context>
<input>
【Situation actuelle (informations confidentielles masquées)】

### Ce qui s'est produit
-

### Quand l'incident est-il survenu ?
-

### Impact sur le client
-

### Impact sur l'organisation interne
-

### Faits actuellement confirmés
-

### Informations encore inconnues
-

### Réponses déjà engagées
-

### Délais et contraintes
-
</input>
<constraints>
- Ne transmettez pas de noms de clients, de personnes, de sociétés, d'informations contractuelles ou d'informations d'authentification.
- Distinguez clairement les faits et les hypothèses, et indiquez « (hypothèse) » pour toute information hypothétique.
- N'affirmez pas les causes ou la responsabilité, et ne mentionnez aucune indemnisation ou réparation.
- Indiquez que le brouillon d'explication ou d'excuse destiné au client doit être vérifié par le responsable hiérarchique et le service juridique.
- Le résultat de l'IA est un support de décision. La décision finale doit toujours être prise par un humain.
</constraints>
<output_format>
1. Séparation des faits et des hypothèses
2. Organisation de l'impact (client, organisation interne)
3. Points à vérifier aujourd'hui (dans les 24 heures)
4. Éléments à transmettre au client (brouillon)
5. Décisions à prendre en interne
6. Actions de réponse initiale
7. Plan de réponse sur 72 heures
8. Nécessité d'une escalade et recommandation
</output_format>
```
