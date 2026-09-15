# Gestion et arbitrage des modifications de périmètre (Scope Change) — Exemple pratique

## Cas d'usage (Use Case)

Ce scénario modélise l'apparition de demandes d'évolution ou de fonctionnalités complémentaires émanant du client en phase intermédiaire de développement.

L'objectif est d'utiliser l'IA pour objectiver l'écart par rapport au périmètre initialement contractualisé, cartographier les impacts opérationnels (charges, délais, coûts) et bâtir des scénarios d'arbitrage clairs à soumettre à la gouvernance.

---

## Fichiers de contexte utilisés

- `contexts/PM_CONTEXT.md`
- `contexts/SCOPE_CHANGE_CONTEXT.md`

---

## Données d'entrée anonymisées (Sanitized Input)

> **Avertissement :** Les données ci-dessous sont entièrement fictives. Aucun nom réel de client, de projet ou d'individu n'est mentionné.

```
Projet : Projet Alpha (Fictif)
Phase opérationnelle : Milieu de développement (70% d'avancement global)

【Demandes d'évolution exprimées】
Le Contact client A a formulé les demandes d'ajouts suivantes :

Demande 1 : Intégrer un module d'exportation de données en masse (Batch Export) dans le back-office d'administration
Demande 2 : Ajouter un graphique comparatif d'évolution mensuelle (M/M-1) sur le tableau de bord
Demande 3 : Enrichir les règles de validation et de contrôle de cohérence sur le formulaire d'inscription (spécifications précises en attente)

【Origine de la demande】
- Exigence émise par la direction générale du client pour « améliorer l'ergonomie opérationnelle des équipes terrain »
- Besoins d'exploitation découverts tardivement par le métier, non identifiés lors des ateliers de cadrage initial

【Périmètre initialement contractualisé (Baseline Scope)】
- Back-office : consultation, recherche multicritère et export unitaire exclusivement
- Tableau de bord : restitution analytique circonscrite à l'exercice en cours
- Contrôles de formulaires : strictement limités aux règles recensées dans le dossier de spécifications fonctionnelles v1.0

【Charge prévisionnelle estimée】
- Export en masse : 3 à 5 jours-hommes (estimation brute à affiner)
- Graphique comparatif : 2 à 3 jours-hommes (estimation brute à affiner)
- Règles de validation additionnelles : chiffrage impossible en l'absence de spécifications détaillées

【Composants applicatifs impactés】
- Risque d'incohérence entre les formats d'export unitaire existants et l'export en masse
- Impact potentiel sur le schéma de base de données à confirmer

【Contrainte calendaire impérative】
- Échéance finale de livraison : dans 4 semaines (20 jours ouvrés)
- Date de déploiement non négociable (annoncée publiquement en interne par le client)

【Contrainte budgétaire】
- Aucun accord de financement complémentaire conclu à ce stade
- Sensibilité et acceptation du client quant à une facturation d'avenant non qualifiées

【Arbitrages à instruire auprès du client】
- Hiérarchisation des 3 demandes (caractère impératif ou négociable)
- Obtention des spécifications précises de la Demande 3
- Acceptation formelle des impacts (surcoût financier et/ou décalage de livraison)
```

---

## Prompt

```text
Après avoir intégré les fichiers de contexte ci-dessous, analyse la demande d'évolution de périmètre et prépare la grille d'arbitrage projet.

【Fichiers de contexte】
- contexts/PM_CONTEXT.md
- contexts/SCOPE_CHANGE_CONTEXT.md

【Données de situation】
(Coller les données d'entrée anonymisées ci-dessus)

Structure ton analyse selon les axes suivants :
1. Qualification des demandes d'évolution
2. Écart caractérisé par rapport au périmètre initial (Scope Baseline)
3. Matrice des impacts collatéraux (architecture, tests, cohérence)
4. Évaluation de la charge de travail additionnelle
5. Impact sur le chemin critique et la date de livraison
6. Risques contractuels et financiers
7. Clarifications préalables à exiger du client
8. Scénarios d'arbitrage à présenter (options A, B, C)
9. Circuit d'escalade managériale
```

---

## Livrable attendu de l'IA (Expected Output)

Exemple illustratif de la restitution attendue. Les résultats réels varient selon le modèle et les données injectées.

---

### 1. Qualification des demandes d'évolution

| # | Libellé de la demande | Statut dans le périmètre initial | Typologie de modification |
|---|---|---|---|
| 1 | Module d'export en masse en back-office | Hors périmètre (Out of scope) | Demande d'évolution majeure |
| 2 | Graphique comparatif mensuel sur le tableau de bord | Hors périmètre (Out of scope) | Demande d'évolution mineure |
| 3 | Nouvelles règles de validation de saisie | Hors spécifications v1.0 | Extension de périmètre (non qualifiée) |

---

### 2. Écart caractérisé par rapport au périmètre initial (Scope Baseline)

- **Back-office** : Le périmètre validé couvre uniquement la recherche et l'export fiche par fiche. L'export groupé nécessite un nouveau composant asynchrone pour éviter les surcharges serveurs.
- **Tableau de bord** : Limité au cumul de l'exercice courant. La comparaison historique implique d'agréger des données antérieures.
- **Formulaire** : Strictement circonscrit à la matrice de validation validée en recette fonctionnelle.

Aucune de ces trois exigences ne figure dans les documents contractuels de cadrage.

---

### 3. Matrice des impacts collatéraux

| Domaine d'impact | Conséquence opérationnelle |
|---|---|
| Documentation / Spécifications | Nécessité de réviser et faire signer les spécifications détaillées avant tout codage |
| Effort de développement | Développement supplémentaire sur 3 modules distincts |
| Effort de qualification | Conception de nouveaux jeux de tests et cas limites |
| Cohérence fonctionnelle | Risque de rupture de format de restitution de données entre exports unitaires et exports en masse |
| Modèle de données | Risque de refonte de requêtes SQL complexes pour l'historique M/M-1 |

---

### 4. Évaluation de la charge de travail additionnelle

| Demande | Estimation prévisionnelle | Commentaire technique |
|---|---|---|
| Export groupé | 3 à 5 jours-hommes | Sujet à validation de l'architecture d'exécution |
| Graphique comparatif | 2 à 3 jours-hommes | Peut augmenter si des indexations DB sont requises |
| Nouvelles validations | Indéterminée | Chiffrage impossible sans les règles métier exactes |
| **Total prévisionnel** | **5 à 8 j/h minimum** | Sous réserve de la complexité de la Demande 3 |

---

### 5. Impact sur le chemin critique et la date de livraison

Sur un solde calendaire de 4 semaines (20 jours ouvrés) et compte tenu du retard résiduel en cours de résorption, l'injection de 5 à 8 jours de dev additionnels comprimerait mortellement la phase de tests d'intégration.

- **Acceptation intégrale des 3 demandes** : Impossibilité matérielle de tenir le jalon de livraison sans dérive calendaire majeure.
- **Acceptation partielle sélective** : Faisable uniquement sur un volume résiduel strictement encadré (ex. 2 jours).
- **Règles de validation (Demande 3)** : À exclure de la livraison nominale en raison du flou de spécification.

**Conclusion calendaire : L'intégration complète à date constante est irréalisable.**

---

### 6. Risques contractuels et financiers

> **Avertissement :** Les incidences contractuelles et de refacturation exigent une consultation préalable de la direction commerciale et du service juridique.

- Les demandes ne figurant pas au cahier des charges, leur prise en charge sans avenant formel dégraderait la rentabilité du projet et créerait un précédent juridique défavorable.
- L'acceptation verbale ou informelle sans notification écrite d'impact calendaire engagerait la responsabilité du prestataire en cas de non-respect de l'échéance finale.

---

### 7. Clarifications préalables à exiger du client

- Établir la hiérarchie de valeur métier entre les 3 demandes (définir les éléments impératifs vs accessoires)
- Obtenir sous 48h les règles de gestion précises de la Demande 3
- Confirmer si le client est prêt à arbitrer entre un report de date ou un financement par avenant

---

### 8. Scénarios d'arbitrage à présenter (Options A, B, C)

| Option | Périmètre traité | Calendrier de livraison | Incidence financière |
|---|---|---|---|
| **Option A : Prise en compte globale avec report** | Intégration des 3 demandes après stabilisation des spécifications | Report du jalon de 2 à 3 semaines | Émission d'un avenant au forfait |
| **Option B : Déploiement du socle nominal et version v1.1 rapide** | Maintien strict du périmètre initial pour la mise en prod dans 4 semaines ; livraison des évolutions dans un sprint v1.1 dédié | Jalon initial garanti | Avenant pour le lot v1.1 |
| **Option C : Substitution de périmètre (Trade-off)** | Intégration de la Demande 1 en contrepartie du déscopage d'une fonctionnalité initiale de charge équivalente | Jalon initial maintenu | Neutre budgétairement |

---

### 9. Circuit d'escalade managériale

**Escalade interne obligatoire :**
- Information immédiate de la direction de projet et du responsable commercial
- Interdiction stricte aux équipes de développement de commencer tout codage sur ces demandes sans ordre de service ou avenant signé
- Validation collégiale de l'argumentaire avant transmission des options au client

---

## Points de contrôle humain (Human Review Points)

Avant de formaliser la réponse au client, le chef de projet doit contrôler :

- L'exactitude contractuelle de la délimitation du périmètre initial vis-à-vis des annexes signées
- La solidité de l'estimation de charge validée par l'équipe technique
- L'adéquation des options proposées avec la politique commerciale du compte
- La neutralité et la fermeté du discours : valoriser la volonté de service tout en posant la réalité physique des contraintes de délai et de budget

---

## Consignes de sécurité et avertissements (Caution)

> [!IMPORTANT]
> Les données utilisées dans ce document sont purement fictives.
>
> Ne saisissez jamais d'éléments contractuels confidentiels, de taux journaliers réels ou d'identités réelles dans un outil d'IA.
>
> **L'IA ne prend pas de décisions contractuelles.** Toute modification d'échéance, de budget ou de responsabilité juridique requiert la validation formelle des signataires habilités de l'entreprise.
