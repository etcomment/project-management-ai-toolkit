# Compte rendu de réunion et plan d'actions (Meeting Minutes & TODOs) — Exemple pratique

## Cas d'usage (Use Case)

Ce scénario illustre la conversion de notes brutes prises au vol lors d'un comité hebdomadaire en un compte rendu structuré comprenant la synthèse, les décisions validées, les points en suspens, les actions à mener (TODO) et les points de vigilance pour l'échéance suivante.

L'objectif est d'accélérer la formalisation post-réunion tout en garantissant la rigueur de suivi.

---

## Fichiers de contexte utilisés

- `contexts/PM_CONTEXT.md`
- `contexts/MEETING_MINUTES_CONTEXT.md`

---

## Données d'entrée anonymisées (Sanitized Input)

> **Avertissement :** Les données ci-dessous sont entièrement fictives. Aucun nom réel de client, de projet ou d'individu n'est mentionné.

```
Objet de la réunion : Comité d'avancement hebdomadaire
Type de réunion : Point régulier client / prestataire
Date : Semaine 9 (S9), Mercredi
Rôles des participants : Chef de Projet (prestataire), Lead Développeur (prestataire), Contact client A

【Notes brutes de réunion (prises de notes télégraphiques)】

- Action de la semaine précédente : retour sur les spécifications de données → apporté en séance par le Contact client A (détails ci-dessous)
- Orientations actées sur les spécifications d'interfaces de données :
  - Rubrique X : déscopée de la version actuelle
  - Rubrique Y : spécification simplifiée à retenir (le Contact client A transmettra une note de cadrage séparée)
  - Rubrique Z : maintien des spécifications initiales sans altération
- Développement du module externe : cible fixée à la fin de semaine prochaine pour achèvement (rattrapage de planning enclenché)
- Lancement de la conception des tests → le Lead Tech prévoit de démarrer dès lundi prochain
- Alerte sur la fenêtre de test → le Lead Tech indique : « 5 jours ouvrés de tests d'intégration, c'est intenable »
  - Le Chef de Projet répond qu'il faut étudier une extension du calendrier, mais aucune décision définitive n'est encore actée
- Comité Go/No-Go de validation de mise en production → confirmation de date demandée au Contact client A ; celui-ci indique devoir valider auprès de sa hiérarchie. En attente de son retour
- Prochain point d'avancement : Mercredi prochain
  - Le Contact client A doit apporter les arbitrages de sa direction
```

---

## Prompt

```text
Après avoir intégré les fichiers de contexte ci-dessous, structure et formalise les notes brutes de réunion en un compte rendu professionnel assorti d'un plan d'actions.

【Fichiers de contexte】
- contexts/PM_CONTEXT.md
- contexts/MEETING_MINUTES_CONTEXT.md

【Notes de réunion】
(Coller les données d'entrée anonymisées ci-dessus)

Structure ta restitution selon les axes suivants :
1. Synthèse managériale de la réunion
2. Décisions actées (Decisions)
3. Points en suspens et arbitrages ouverts (Open Issues)
4. Registre des actions / TODO (avec responsable et date butoir)
5. Actions sans responsable identifié (points aveugles)
6. Ordre du jour et points à trancher lors de la prochaine séance
7. Risques et facteurs de vigilance
```

---

## Livrable attendu de l'IA (Expected Output)

Exemple illustratif de la restitution attendue. Les résultats réels varient selon le modèle et les données injectées.

---

### 1. Synthèse managériale de la réunion

Lors du comité hebdomadaire de la Semaine 9, les orientations sur les spécifications d'interfaces de données ont été arrêtées avec le Contact client A (déscopage de X, simplification de Y, maintien de Z). Le développement des flux externes cible un achèvement en fin de semaine prochaine. La conception du plan de tests débutera lundi prochain sous la responsabilité du Lead Développeur ; toutefois, l'alerte sur la brièveté de la fenêtre de qualification (5 jours) impose un arbitrage rapide sur le calendrier. La fixation de la date du comité Go/No-Go reste soumise à validation hiérarchique côté client.

---

### 2. Décisions actées (Decisions)

| # | Décision actée |
|---|---|
| 1 | Interfaces de données : exclusion de la rubrique X du périmètre de la version actuelle |
| 2 | Interfaces de données : simplification des spécifications pour la rubrique Y |
| 3 | Interfaces de données : conservation des exigences initiales pour la rubrique Z |
| 4 | Cible d'achèvement du développement des flux externes fixée à la fin de la Semaine 10 |
| 5 | Lancement de la conception du plan de tests acté pour lundi prochain par le Lead Tech |

---

### 3. Points en suspens et arbitrages ouverts (Open Issues)

| # | Sujet ouvert | Action attendue / Interlocuteur |
|---|---|---|
| 1 | Prolongation éventuelle de la fenêtre de tests | Arbitrage tripartite requis : Chef de Projet / Direction / Client |
| 2 | Date du comité de validation Go/No-Go | En cours de validation par le Contact client A auprès de sa direction |
| 3 | Spécification technique détaillée de la simplification de Y | Attente de la note de cadrage du Contact client A |

---

### 4. Registre des actions / TODO

| # | Action | Responsable | Échéance |
|---|---|---|---|
| 1 | Finalisation des développements des interfaces externes | Équipe Dev | Fin de Semaine 10 |
| 2 | Initialisation de la rédaction du plan de tests | Lead Développeur | Lundi de Semaine 10 |
| 3 | Réception et accusé de réception de la note de cadrage sur la rubrique Y | Chef de Projet | Dès émission par le client |
| 4 | Instruction de l'impact calendaire d'une extension de la phase de test | Chef de Projet | Avant le prochain comité |
| 5 | Relance sur la date du comité de décision Go/No-Go | Chef de Projet | Prochain comité d'avancement |

---

### 5. Actions sans responsable identifié (points aveugles)

- Revue d'impact technique de la note de cadrage sur Y : qui instruit et valide la faisabilité dès réception de la note du client ? À attribuer au Lead Développeur.

---

### 6. Ordre du jour et points à trancher lors de la prochaine séance

Points prioritaires du comité de Mercredi prochain :

- Confirmation de la date du comité Go/No-Go (retour de la direction client)
- Présentation de la proposition du Chef de Projet concernant le recalibrage de la période de test
- Contrôle de l'avancement des flux externes vis-à-vis de l'objectif de fin de semaine
- Revue du démarrage de la conception des tests

---

### 7. Risques et facteurs de vigilance

| Risque | Analyse et impact opérationnel |
|---|---|
| Compression de la qualification | La fenêtre de 5 jours est jugée intenable par l'équipe technique. Maintenir cette durée sans arbitrage fait peser un risque critique sur la stabilité de la mise en production |
| Retard d'instruction sur la rubrique Y | Si la note de cadrage tarde à parvenir, le développement risque de subir un décalage supplémentaire lors de la phase de tests unitaires |
| Carence de critères d'homologation | L'absence d'accord formel sur les critères d'acceptation du comité Go/No-Go expose à un refus de recette en fin de parcours |

---

## Points de contrôle humain (Human Review Points)

Avant toute transmission ou diffusion, le chef de projet doit vérifier :

- La stricte conformité des décisions actées avec les débats réels en réunion (absence de surinterprétation de l'IA)
- L'exhaustivité des points en suspens et la fidélité des attributions
- Le réalisme des dates butoirs et la désignation nominative précise des acteurs
- L'adaptation diplomatique des formulations si le compte rendu est partagé avec le client
- La prise en compte des non-dits ou signaux faibles perçus pendant la séance

---

## Consignes de sécurité et avertissements (Caution)

> [!IMPORTANT]
> Les informations de cet exemple sont purement fictives.
>
> Toute note de réunion réelle doit faire l'objet d'un filtrage et d'une anonymisation stricte de ses données sensibles avant injection dans un outil d'IA.
>
> **L'IA ne se substitue pas à la responsabilité du chef de projet.** Le compte rendu engage contractuellement l'équipe auprès du client dès lors qu'il est émis.
