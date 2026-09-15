# Guide de sécurité et d'usage responsable de l'IA / AI Safety Guide

---

## Introduction

Ce guide définit les règles impératives de sécurité, de confidentialité et de déontologie professionnelle à respecter lors de l'utilisation des fichiers de contexte et des modèles de requêtes de ce dépôt avec des services d'IA générative.

**Les sorties de l'IA ne remplacent en aucun cas l'arbitrage managérial ou professionnel. Tout contenu généré doit impérativement être relu, vérifié et validé par un responsable humain avant d'être exploité.**

---

## Informations strictement proscrites en entrée des services d'IA

Les données suivantes ne doivent JAMAIS être saisies dans un service d'IA externe (ChatGPT, Gemini, Claude, etc.) :

### Données à caractère personnel et informations clients
- Noms de clients, enseignes et raisons sociales
- Noms, prénoms, fonctions, numéros de téléphone et adresses emails directes de collaborateurs ou d'intervenants clients
- Données personnelles des membres des équipes projets

### Données contractuelles, financières et sensibles
- Contenus intégraux, clauses particulières et conditions financières des contrats
- Informations couvertes par un accord de confidentialité (NDA)
- Détail unitaire des taux journaliers moyens (TJM), marges ou montants confidentiels de devis
- Données financières ou orientations stratégiques internes non publiques

### Comptes rendus intégraux et retranscriptions brutes
- Procès-verbaux et comptes rendus intégraux comportant des noms réels
- Enregistrements ou verbatims bruts de réunions avec les clients
- Notes de séances internes confidentielles

### Secrets techniques et données de production
- Extraits de code source de production (code propriétaire de l'entreprise ou du client)
- Clés d'API, jetons d'accès (tokens), clés privées et secrets d'authentification
- Mots de passe, certificats et identifiants de bases de données
- Adresses IP de production, noms de domaines internes et architectures réseau sensibles
- Rapports d'audit de vulnérabilité ou failles de sécurité non colmatées

---

## Protocole de validation avant saisie

Avant de soumettre une information à une IA, suivez scrupuleusement le logigramme de contrôle suivant :

```text
Données projet à soumettre à l'IA
│
├─ Présence de noms de clients, personnes ou sociétés ?
│    ├─ Oui → Anonymiser / Pseudonymiser
│    └─ Non
│
├─ Présence de clauses contractuelles ou données sous NDA ?
│    ├─ Oui → Proscrire la saisie / Consulter la direction
│    └─ Non
│
├─ Présence de clés API, mots de passe ou tokens ?
│    ├─ Oui → Supprimer impérativement
│    └─ Non
│
├─ Présence de PV intégraux ou de code source brut ?
│    ├─ Oui → Synthétiser et abstraire
│    └─ Non
│
└─ Contrôle des politiques internes, contrats clients et CGU de l'IA
     │
     v
Validation formelle de l'éligibilité des données
     │
     v
Saisie dans l'outil d'IA
     │
     v
Relecture, ajustement et validation humaine des résultats
```

> [!IMPORTANT]
> La responsabilité finale de l'éligibilité des données transmises à un tiers relève exclusivement de l'utilisateur, au regard des règles de sécurité de son organisation, des contrats clients, des accords NDA et des conditions de service des plateformes d'IA.

---

## Table de correspondance pour le masquage et l'anonymisation

Lors de la préparation de vos données opérationnelles, appliquez systématiquement le principe d'abstraction suivant :

| Catégorie d'information | Donnée brute réelle (À proscrire) | Formulation anonymisée conforme |
|---|---|---|
| Nom de client | Société Alpha Solutions SA | Client A (Grand compte du secteur distribution) |
| Intervenant client | Claire Martin | Représentant Client A |
| Chef de projet interne | Thomas Dubois PM | Chef de projet référent |
| Montant contractuel | 280 000 € HT | Enveloppe budgétaire de quelques centaines de k€ |
| Date butoir | 31 mars 2026 | Fin de premier trimestre |
| Extrait de réunion brut | « Claire Martin exige la refonte du module de facturation » | « Le client a émis une demande d'évolution sur un composant clé (non arbitrée) » |
| Clé d'API | sk-xxxxxxxxxxxxxxxxxx | [SUPPRIMÉ] |

---

## Exemples d'entrées conformes et sécurisées

Voici des exemples types d'informations convenablement anonymisées pouvant être soumises sans risque opérationnel :

### Exemple conforme 1 : Structuration du suivi d'avancement

```
Merci de structurer la situation d'avancement de la semaine selon une perspective Chef de Projet :

- Phase : Revue de conception achevée, lancement de la phase de réalisation
- Tâches achevées : Validation des maquettes UX (3 écrans clés), modèle de données figé
- Points en attente : Spécifications de l'API partenaire (en attente de retour client)
- Retard constaté : Mise à disposition de l'environnement de recette décalée de 2 jours ouvrés
- Risque identifié : L'absence de stabilisation de l'API bloque le démarrage de 4 fonctionnalités
- Planning semaine suivante : Lancement du sprint sur 6 fonctionnalités, comité hebdomadaire client
```

### Exemple conforme 2 : Revue de criticité d'un backlog d'incidents

```
Merci d'auditer ce registre de points durs sous l'angle PM.
Identifiez les tâches orphelines, les échéances manquantes et les périmètres d'impact imprécis.

| N° | Incident / Point dur | Statut | Responsable (Rôle) | Échéance |
|---|---|---|---|---|
| 1 | Validation des specs de l'API externe | Non démarré | Non assigné | Non fixée |
| 2 | Configuration de l'environnement de test | En cours | Ingénieur DevOps | Lundi prochain |
| 3 | Demande d'évolution fonctionnelle client | En attente | — | — |
```

### Exemple conforme 3 : Projet de communication client

```
Merci de préparer un projet de courriel destiné au client dans le contexte suivant :

- Situation : Les spécifications de l'API externe n'étant pas arrêtées, les développements associés sont suspendus
- Position de l'équipe : Une stabilisation d'ici la fin de semaine permettra de neutraliser tout décalage du jalon de livraison
- Décisions attendues du client : Date cible de livraison des spécifications ou validation d'une implémentation simulée (mock)
- Recommandation de posture : Rester constructif et partenarial, sans imputer unilatéralement la faute
- Note : Ce texte constitue une base préparatoire qui sera relue et validée par le chef de projet avant diffusion.
```

---

## Exemples d'entrées dangereuses proscrites

Ne formulez JAMAIS vos invites de la manière suivante :

### Exemple proscrit 1 : Données nominatives et propos attribués

```
❌ EXEMPLE DANGEREUX À PROSCRIRE
Mme Claire Martin de chez Alpha Solutions m'a dit lors du copil : « Le 31 mars est une date
impérative non négociable ». Notre chef de projet Thomas Dubois lui a dit qu'on allait voir,
mais en réalité nous serons en retard. Rédige un mail pour lui annoncer.
```
→ *Gravité : Divulgation de données personnelles, citations directes d'intervenants et secrets d'affaires. Anonymisez impérativement.*

### Exemple proscrit 2 : Divulgation de secrets techniques

```
❌ EXEMPLE DANGEREUX À PROSCRIRE
Voici notre configuration de production : la clé API est « sk-xxxxxxxxxx » et le mot de passe
de la base de données est « pass1234 ». Y a-t-il un problème de sécurité dans cette architecture ?
```
→ *Gravité : Risque critique de compromission de sécurité. Ne saisissez jamais d'identifiants ou secrets de production.*

### Exemple proscrit 3 : Injection brute de procès-verbaux

```
❌ EXEMPLE DANGEREUX À PROSCRIRE
Résume ce compte rendu :
[Copier-coller de l'intégralité du PV avec noms des participants, rémunérations, clauses juridiques...]
```
→ *Gravité : Violation des règles de confidentialité et exposition de données sensibles. Isolez et synthétisez les faits pertinents au préalable.*

---

## Précautions spécifiques pour les documents contractuels et livrables clients

Une vigilance absolue s'impose dès lors que les sorties de l'IA sont exploitées pour :

- Des documents officiels ou courriers contractuels destinés au client
- Des comptes rendus d'incidents (post-mortems), bilans de crise ou rapports d'avancement
- Des propositions commerciales, avenants, engagements de périmètre ou devis
- Des engagements fermes sur le calendrier de livraison ou les critères d'acceptation qualité

**NE DIFFUSEZ JAMAIS DIRECTEMENT UN LIVRABLE PRODUIT PAR UNE IA SANS VALIDATION HUMAINE.**

Vérifiez scrupuleusement les 5 points suivants avant tout partage :

1. **Exactitude factuelle** : Les événements, dates et descriptions techniques sont-ils rigoureusement vrais ?
2. **Adéquation contextuelle** : Le contenu reflète-t-il fidèlement l'historique et la réalité du projet ?
3. **Justesse relationnelle** : Le ton est-il adapté à la relation partenariale et contractuelle avec le destinataire ?
4. **Maîtrise contractuelle** : Les clauses de responsabilité, de délais et de budget sont-elles conformes aux engagements ?
5. **Circuit de validation** : Les validations requises (Direction de projet, Direction commerciale, Juridique) ont-elles été formellement recueillies ?

---

## Vérification préalable des politiques internes et conditions d'usage (CGU)

Avant d'introduire des informations professionnelles dans un service d'IA générative, contrôlez systématiquement :

- Les Conditions Générales d'Utilisation (CGU) de l'outil d'IA
- La politique de confidentialité de l'éditeur
- **Les clauses d'utilisation des données (les données saisies servent-elles à l'entraînement des modèles de l'éditeur ?)**
- La charte informatique et la politique de sécurité des systèmes d'information (PSSI) de votre entreprise
- Les engagements contractuels et clauses de confidentialité (NDA) conclus avec vos clients

Certaines organisations prohibent formellement le téléversement de données métier sur des services d'IA publics. Assurez-vous de disposer des habilitations requises.

---

## Domaines d'exclusion formelle de l'IA

Les livrables de l'IA ne doivent **en aucun cas servir de fondement unilatéral** pour les catégories d'arbitrage suivantes, qui relèvent exclusivement du jugement d'experts humains habilités :

- Arbitrages et engagements contractuels, avenants, devis fermes et bons de commande
- Décisions et interprétations juridiques, fiscales, réglementaires ou de droit social
- Certification et diagnostics formels de sécurité des systèmes d'information
- Engagements juridiques fermes de dates de livraison ou de niveaux de service (SLA)
- Évaluation disciplinaire, notation individuelle ou décisions RH relatives aux collaborateurs

---

## Documents associés

- Clause de non-responsabilité : [docs/legal/DISCLAIMER.md](legal/DISCLAIMER.md)
- Conditions d'utilisation : [docs/legal/TERMS.md](legal/TERMS.md)
- Guide d'utilisation opérationnel : [docs/usage-guide.md](usage-guide.md)
- Charte de la communauté : [docs/community.md](community.md)
