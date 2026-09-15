# Élaboration d'un rapport d'avancement (Status Report) — Exemple pratique

## Cas d'usage (Use Case)

Ce scénario illustre la rédaction d'un rapport d'avancement hebdomadaire (Flash report) destiné à la fois au management interne et au client.

L'objectif est d'exploiter l'IA pour synthétiser les réalisations hebdomadaires, formaliser les retards et produire des déclinaisons adaptées aux différentes parties prenantes.

---

## Fichiers de contexte utilisés

- `contexts/PM_CONTEXT.md`
- `contexts/STATUS_REPORT_CONTEXT.md`

---

## Données d'entrée anonymisées (Sanitized Input)

> **Avertissement :** Les données ci-dessous sont entièrement fictives. Aucun nom réel de client, de projet ou d'individu n'est mentionné.

```
Projet : Projet Alpha (Fictif)
Semaine de reporting : Semaine 8 (S8)
Destinataires : Direction de projet interne, Contact client A

【Réalisations achevées cette semaine】
- Revue de conception des écrans (vues liste et détail) finalisée
- Intégration des retours sur le modèle de données (Dossier d'architecture DB v1.1) finalisée
- Développement du socle des interfaces externes achevé (tests unitaires non exécutés)

【Tâches non finalisées (reportées sur le cycle suivant)】
- Recette unitaire des interfaces externes (reportée en début de semaine prochaine)
- Version initiale du plan de conception des tests (démarrage prévu courant semaine prochaine)

【Chantiers en dérive / retard】
- Interfaces externes : 1 semaine de retard sur le planning initial
  Cause racine : développement mis en attente en raison d'arbitrages de spécifications non tranchés

【Points de blocage (Issues)】
- Demande d'arbitrage sur les spécifications de données auprès du contact client A restée sans réponse (en attente depuis S7)
- Divergence technique sur les interfaces backend partiellement levée lors du point de cadrage hebdomadaire, 1 point restant en suspens

【Risques identifiés】
- Absence d'initialisation des plans de tests risquant de comprimer la phase aval de validation
- Absence de calage du calendrier des tests d'intégration avec l'opérateur du système externe

【Attentes et arbitrages client (Blockers)】
- Validation des spécifications de flux de données (relance effectuée avec date limite fixée à cette fin de semaine)

【Planning et engagements de la semaine suivante】
- Exécution des tests unitaires sur les interfaces externes
- Rédaction du premier jet du plan de conception des tests
- Comité d'avancement hebdomadaire avec le contact client A
- Arbitrage final sur le dernier point d'interface backend
```

---

## Prompt

```text
Après avoir intégré les fichiers de contexte ci-dessous, rédige les rapports d'avancement à partir des données de la semaine.

【Fichiers de contexte】
- contexts/PM_CONTEXT.md
- contexts/STATUS_REPORT_CONTEXT.md

【Données d'avancement】
(Coller les données d'entrée anonymisées ci-dessus)

Produis les livrables suivants :
1. Rapport d'avancement pour le management interne (Direction de projet)
2. Rapport d'avancement pour le client
3. Synthèse managériale exécutive pour la direction (3 lignes maximum)
4. Tableau de bord des risques qualifié
5. Plan d'actions immédiates (Next Actions)
```

---

## Livrable attendu de l'IA (Expected Output)

Exemple illustratif de la restitution attendue. Les résultats réels varient selon le modèle et les données injectées.

---

### 1. Rapport d'avancement pour le management interne (Direction de projet)

**Objet :** Projet Alpha — Rapport d'avancement Semaine 8

**Situation globale :**
Cette semaine, la revue de conception des écrans et la mise à jour du dossier d'architecture de données ont été menées à bien. Le socle des interfaces externes a été développé, mais accuse un retard d'une semaine consécutif à l'attente de validations de spécifications. Un plan d'absorption est enclenché dès la levée du blocage.

**Réalisations achevées :**
- Validation de la revue de conception des écrans (listes et détails)
- Approbation du dossier d'architecture de données v1.1
- Finalisation du socle de code des flux externes

**Restes à faire reportés :**
- Recette unitaire des flux externes (planifiée début S9)
- Élaboration du plan de conception des tests (démarrage planifié courant S9)

**Dérives et points d'attention :**
- Retard d'une semaine sur les interfaces externes. Reprise du nominal tributaire du retour client attendu en fin de semaine.
- Conception des tests non initiée : lancement prioritaire en début de S9 pour sécuriser le chemin critique des recettes.

**Arbitrages en attente côté client :**
- Validation formelle des spécifications de données (échéance fixée à cette fin de semaine).

**Priorités de la semaine prochaine :**
Exécution des tests unitaires des flux externes, initialisation du plan de tests, tenue du comité d'avancement hebdomadaire.

---

### 2. Rapport d'avancement pour le client

**Objet :** 【Projet Alpha】Point d'avancement hebdomadaire — Semaine 8

Madame, Monsieur [Contact A],

Veuillez trouver ci-dessous l'état d'avancement des travaux pour cette Semaine 8.

**Avancées de la semaine :**
- Les revues de conception des écrans (écrans listes et fiches détaillées) ont été finalisées avec succès.
- La mise à jour des spécifications techniques de bases de données a été intégrée.
- Le développement initial du module d'interfaçage externe est achevé.

**Objectifs pour la semaine prochaine :**
- Réalisation de la recette unitaire des modules d'interfaçage.
- Structuration initiale du plan de tests de recette.
- Alignement sur les derniers arbitrages techniques lors de notre comité hebdomadaire.

**Points d'attention et arbitrages requis :**
Concernant la validation des spécifications de flux de données soumises la semaine passée, nous vous remercions de bien vouloir nous confirmer votre accord d'ici la fin de cette semaine.
Ce retour conditionne directement le maintien de la trajectoire des étapes ultérieures.

Restant à votre entière disposition,

Cordialement,

---

### 3. Synthèse managériale exécutive pour la direction (3 lignes max)

Retard d'une semaine enregistré sur les interfaces externes en raison d'un arbitrage client en suspens, attendu en fin de semaine pour rétablissement du nominal. Lancement prioritaire des plans de tests planifié dès la semaine prochaine afin d'annihiler tout risque d'étranglement sur la phase aval.

---

### 4. Tableau de bord des risques qualifié

| Risque | Niveau d'impact | Dispositif de maîtrise / Plan d'action |
|---|---|---|
| Persistance du retard sur les flux externes | Élevé : risque de propagation sur le chemin critique | Échéance formelle notifiée au client. Dispositif de rattrapage activable dès réception |
| Retard dans l'initialisation du plan de tests | Élevé : compression de la phase de qualification aval | Démarrage ferme semaine prochaine, ressources et rétroplanning à verrouiller |
| Absence de coordination des tests avec le système tiers | Modéré : risque de décalage des jalons d'intégration | Enclenchement de la synchronisation des calendriers dès la semaine prochaine |

---

### 5. Plan d'actions immédiates (Next Actions)

| # | Action | Responsable | Échéance |
|---|---|---|---|
| 1 | Relance et sécurisation du retour du Contact client A sur les spécifications | Chef de Projet | Fin de semaine en cours |
| 2 | Exécution des tests unitaires sur les interfaces externes | Équipe Dev | Première moitié de S9 |
| 3 | Lancement de la conception du plan de tests et cadrage des ressources | Chef de Projet / Lead Tech | Courant S9 |
| 4 | Arbitrage final sur le dernier point d'interface backend | Lead Développeur | Comité d'avancement S9 |
| 5 | Calage du calendrier des tests d'intégration avec le partenaire tiers | Chef de Projet | Courant S9 |

---

## Points de contrôle humain (Human Review Points)

Avant toute émission opérationnelle, le chef de projet doit vérifier scrupuleusement :

- L'adéquation du ton et des formules de politesse du message client avec la culture partenariale en vigueur
- L'exactitude factuelle de la justification du retard vis-à-vis des comptes rendus de comités antérieurs
- Le dosage de l'injonction sur les relances client (éviter l'agressivité tout en soulignant avec fermeté l'impact sur les délais)
- La cohérence de la criticité des risques et la viabilité des actions de remédiation
- L'affectation nominative effective des responsables sur le tableau des actions
- L'adéquation du niveau de synthèse interne avec les attentes spécifiques de la direction

---

## Consignes de sécurité et avertissements (Caution)

> [!IMPORTANT]
> Les données de cet exemple sont strictement fictives. Aucun nom réel de client, de projet ou de personne physique n'est mentionné.
>
> Toute donnée réelle doit impérativement être anonymisée et débarrassée de toute information confidentielle avant soumission à l'IA.
>
> **Les livrables de l'IA ne se substituent pas à la responsabilité managériale.** Le chef de projet demeure seul garant de l'exactitude des informations transmises aux parties prenantes.
