# Revue des problèmes et analyse des risques (Issue & Risk Review) — Exemple pratique

## Cas d'usage (Use Case)

Ce scénario illustre l'exploitation de l'IA pour auditer le registre des problèmes (Issues) d'un projet, identifier les manques de pilotage opérationnel et faire émerger les risques sous-jacents.

Il s'agit d'automatiser et de fiabiliser la revue périodique du tableau de bord des alertes et des risques.

---

## Fichiers de contexte utilisés

- `contexts/PM_CONTEXT.md`
- `contexts/ISSUE_RISK_CONTEXT.md`

---

## Données d'entrée anonymisées (Sanitized Input)

> **Avertissement :** Les données ci-dessous sont entièrement fictives. Aucun nom réel de client, de projet ou d'individu n'est mentionné.

```
Projet : Projet Alpha (Fictif)
Date de revue : Semaine 9 (S9)

【Registre des problèmes / Alertes (Issues)】

No.1
  Titre : Spécifications des interfaces de données non stabilisées
  Statut : En cours de traitement
  Responsable : Lead Développeur
  Échéance : Fin de semaine en cours (en attente retour client)
  Périmètre d'impact : Ensemble du module d'interfaçage externe
  Plan d'action : Demande de validation formelle transmise au Contact client A. En attente de retour
  Dépendance externe : Arbitrage indispensable du Contact client A

No.2
  Titre : Plan de conception des tests non rédigé
  Statut : Non démarré
  Responsable : Non assigné
  Échéance : Non définie
  Périmètre d'impact : Ensemble de la phase de qualification (tests d'intégration et recette usine)
  Plan d'action : Démarrage envisagé la semaine prochaine
  Dépendance externe : Aucune

No.3
  Titre : Divergence d'interprétation sur l'architecture d'interface backend
  Statut : Partiellement levé, 1 point résiduel en suspens
  Responsable : Lead Développeur, Référent Backend
  Échéance : Comité technique hebdomadaire de la semaine prochaine
  Périmètre d'impact : Flux d'échanges entre couches frontend et backend
  Plan d'action : Arbitrage technique définitif lors du prochain comité
  Dépendance externe : Aucune

No.4
  Titre : Calendrier des tests d'intégration avec le partenaire externe non synchronisé
  Statut : Non démarré
  Responsable : Chef de Projet
  Échéance : Non définie
  Périmètre d'impact : Période globale des tests d'intégration
  Plan d'action : Initialisation des démarches de calage la semaine prochaine
  Dépendance externe : Disponibilité et planning de l'homologue technique externe (Contact B)

No.5
  Titre : Date et modalités du comité de validation de mise en production (Go/No-Go) non fixées
  Statut : Non démarré
  Responsable : Inconnu
  Échéance : Inconnue
  Périmètre d'impact : Procédure globale de mise en production
  Plan d'action : Non défini
  Dépendance externe : Alignement préalable requis avec le Contact client A
```

---

## Prompt

```text
Après avoir intégré les fichiers de contexte ci-dessous, réalise une revue critique et méthodique du registre des problèmes selon les standards d'un pilotage de projet rigoureux.

【Fichiers de contexte】
- contexts/PM_CONTEXT.md
- contexts/ISSUE_RISK_CONTEXT.md

【Registre des problèmes】
(Coller les données d'entrée anonymisées ci-dessus)

Structure ton analyse selon les axes suivants :
1. Typologie et classification des problèmes
2. Réévaluation des priorités opérationnelles
3. Identification des anomalies de gouvernance (responsables ou échéances indéterminés)
4. Alertes dont le périmètre d'impact est sous-évalué ou flou
5. Risques latents et menaces sous-jacentes
6. Sujets nécessitant une escalade managériale immédiate
7. Plan d'actions de remédiation
```

---

## Livrable attendu de l'IA (Expected Output)

Exemple illustratif de la restitution attendue. Les résultats réels varient selon le modèle et les données injectées.

---

### 1. Typologie et classification des problèmes

| Catégorie | N° de problème | Titre |
|---|---|---|
| Dépendance externe / Client | No.1, No.4, No.5 | Spécifications d'interfaces, synchronisation des tests d'intégration, calendrier du comité Go/No-Go |
| Pilotage technique interne (Conception / Dev) | No.3 | Divergence d'interprétation sur l'interface backend |
| Gouvernance et cadrage interne (Planification / Ressources) | No.2 | Plan de conception des tests non rédigé |

---

### 2. Réévaluation des priorités opérationnelles

| N° | Statut actuel | Priorité recommandée | Justification opérationnelle |
|---|---|---|---|
| No.2 | Non démarré, non assigné, sans échéance | **Critique / Urgente** | Le retard sur la stratégie de qualification paralyse l'ensemble des jalons avals. Mobilisation immédiate requise |
| No.1 | En attente de validation client | **Élevée** | Bloque le développement des flux externes. Nécessite une préparation pour engager le dev dès validation reçue |
| No.5 | Responsable et démarche non définis | **Élevée** | Risque d'aboutir au jalon de livraison sans critères d'acceptation ni grille Go/No-Go partagés |
| No.4 | Non démarré, sans échéance | **Moyenne à Élevée** | Si les créneaux du partenaire externe sont restreints, le glissement affectera le jalon de livraison global |
| No.3 | Partiellement levé | **Moyenne** | Concerne un point technique résiduel circonscrit. À trancher formellement lors du prochain point hebdo |

---

### 3. Identification des anomalies de gouvernance (responsables ou échéances indéterminés)

| N° | Anomalie de pilotage | Action corrective préconisée |
|---|---|---|
| No.2 | Ressource non affectée, absence d'échéance | Désigner impérativement un rédacteur et figer le calendrier de livraison dès cette semaine |
| No.5 | Ni responsable, ni échéance, ni plan d'action | Prise en charge directe par le Chef de Projet et cadrage avec le commanditaire |

---

### 4. Alertes dont le périmètre d'impact est sous-évalué ou flou

- **No.5 (Comité de validation Go/No-Go)** : Qualifié sommairement d'impact sur « la mise en production globale », ce point masque l'absence de définition des critères d'acceptation, des seuils de criticité des anomalies bloquantes et de la gouvernance décisionnelle. Il s'agit en réalité d'un risque majeur de non-recette finale.

---

### 5. Risques latents et menaces sous-jacentes

- **Effet ciseau sur le calendrier de qualification** : Le télescopage entre No.2 (tests non cadrés) et No.4 (tests partenaires non synchronisés) fait peser une menace directe d'écrasement ou d'abandon partiel de la couverture de tests
- **Aléa de disponibilité de la tierce partie** : L'inertie du partenaire externe (No.4) peut imposer un décalage unilatéral non maîtrisable
- **Divergence d'acceptation client** : Sans critères d'homologation formalisés (No.5), l'équipe s'expose à un refus de recette pour non-conformité subjective lors de la livraison
- **Défaillance du suivi de la dette qualité** : L'absence de formalisation des anomalies constatées lors des premiers tests risque de fausser la visibilité réelle de la stabilité du système

---

### 6. Sujets nécessitant une escalade managériale immédiate

- **No.5 (Cadrage du Go/No-Go de mise en production)** : Absence totale de pilotage. Le Chef de Projet doit se positionner en propriétaire du sujet, convenir des modalités avec le client et escalader auprès de la direction de projet si un désaccord survient sur les conditions d'acceptation.
- **No.2 (Plan de conception des tests)** : La carence d'affectation met en péril l'organisation. Si une indisponibilité de compétences en interne bloque la désignation, une alerte immédiate pour arbitrage capacitaire doit être transmise à la direction.

---

### 7. Plan d'actions de remédiation

| # | Action | Responsable | Échéance |
|---|---|---|---|
| 1 | No.2 : Affecter un concepteur de tests et arrêter la date de remise du livrable | Chef de Projet | Fin de semaine en cours |
| 2 | No.5 : Enclencher la concertation avec le client sur la date et la grille Go/No-Go | Chef de Projet | Fin de semaine en cours |
| 3 | No.4 : Transmettre la demande de calage d'agenda d'intégration au partenaire tiers | Chef de Projet | Début de semaine prochaine |
| 4 | No.1 : Préparer l'équipe dev pour prise en compte immédiate du retour client | Lead Développeur | Au fil de l'eau |
| 5 | No.3 : Statuer sur le point technique résiduel lors du comité d'architecture | Lead Développeur | Prochain comité technique |

---

## Points de contrôle humain (Human Review Points)

Préalablement à toute décision managériale, vérifiez impérativement :

- L'adéquation de la catégorisation avec la réalité contractuelle de votre engagement
- La conformité de la priorisation avec les échéances fermes négociées avec le client
- La pertinence des risques latents soulevés au regard de l'historique et des pratiques de vos équipes
- La conformité des propositions d'escalade avec les protocoles de gouvernance et circuits hiérarchiques internes
- L'existence éventuelle de contraintes opérationnelles ou politiques internes ignorées par le modèle

---

## Consignes de sécurité et avertissements (Caution)

> [!IMPORTANT]
> Ce cas pratique utilise exclusivement des données fictives. Aucun nom de client, d'entreprise ou de projet réel n'y figure.
>
> Toute donnée issue de projets réels doit être anonymisée et débarrassée de toute information confidentielle avant d'être soumise à un modèle d'IA.
>
> **L'IA ne se substitue pas à la responsabilité managériale.** Toute décision d'escalade, tout engagement contractuel ou toute communication client demeure sous la responsabilité exclusive du chef de projet.
