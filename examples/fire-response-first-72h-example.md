# Gestion de crise : cadrage des 72 premières heures (Fire Response First 72h) — Exemple pratique

## Cas d'usage (Use Case)

Ce scénario simule l'apparition d'une anomalie bloquante majeure à quelques jours d'une mise en production critique.

L'objectif est d'exploiter l'IA durant la fenêtre névralgique des 72 premières heures pour ségréguer faits et suppositions, évaluer le périmètre d'impact, recenser les zones d'ombre et structurer le plan de réaction immédiat.

**Ligne directrice :** Avant toute recherche de responsabilité, la priorité absolue consiste à objectiver les faits, mesurer les impacts réels, poser les scénarios d'arbitrage et orchestrer les actions immédiates.

---

## Fichiers de contexte utilisés

- `contexts/PM_CONTEXT.md`
- `contexts/FIRE_RESPONSE_FIRST_72H.md`

---

## Données d'entrée anonymisées (Sanitized Input)

> **Avertissement :** Les données ci-dessous sont entièrement fictives. Aucun nom réel de client, de projet ou d'individu n'est mentionné.

```
Projet : Projet Alpha (Fictif)
Survenue de l'incident : J-3 avant mise en production (Mardi après-midi)

【Incident constaté】
Lors des ultimes vérifications d'homologation précédant le déploiement en production, une régression critique a été découverte sur le module d'exécution des transactions de paiement.
Sous certaines conditions spécifiques, la transaction ne s'exécute pas et renvoie une erreur système fatale.

【Chronologie et reproductibilité】
- Anomalie détectée en phase finale de recette (Mardi après-midi)
- Antériorité de l'anomalie sur la branche de release non établie
- Comportement reproductible à l'identique sur les environnements de développement et de qualification

【Impacts côté Client / Métier】
- Déploiement général planifié pour ce Vendredi ; le client a d'ores et déjà diffusé la communication de lancement auprès de ses équipes
- Tout report de date générerait une forte perturbation organisationnelle chez le client
- Le Contact client A n'est pas encore informé. Le canal et l'opportunité de l'annonce restent à arbitrer

【Impacts internes et techniques】
- L'équipe technique est mobilisée sur le diagnostic du code
- L'impact collatéral sur les modules connexes n'est pas encore cerné
- Risque d'invalidation et de réexécution complète de la campagne de tests de non-régression

【Faits matériellement établis】
- La transaction de paiement échoue sous un jeu de données spécifique
- Reproductibilité confirmée sur staging et dev
- Conditions exactes de déclenchement en cours de qualification précise

【Éléments non consolidés (inconnues)】
- Cause racine (Root Cause) exacte de l'anomalie
- Périmètre des effets de bord sur le reste de la plateforme
- Charge de travail et délai requis pour le correctif
- Faisabilité du maintien de la mise en production ce Vendredi

【Mesures immédiates déjà prises】
- Enclenchement de l'analyse d'investigation technique (Mardi après-midi)
- Alerte verbale transmise à la direction de projet interne (Mardi en fin de journée)

【Contraintes critiques et échéances】
- Date de mise en production cible : Vendredi
- Plan de communication client déjà déployé en interne par le commanditaire
```

---

## Prompt

```text
Après avoir intégré les fichiers de contexte ci-dessous, analyse et structure le plan de crise opérationnel pour les 72 premières heures.

【Fichiers de contexte】
- contexts/PM_CONTEXT.md
- contexts/FIRE_RESPONSE_FIRST_72H.md

【Données de situation】
(Coller les données d'entrée anonymisées ci-dessus)

Donne la priorité absolue à la clarification des faits, aux impacts, aux options d'arbitrage et au plan d'actions immédiat, avant toute tentative d'analyse des causes profondes.

Structure ta restitution selon les axes suivants :
1. Ségrégation stricte des faits avérés et des conjectures
2. Cartographie du périmètre d'impact
3. Vérifications impératives à mener avant la fin de la journée (J0)
4. Éléments de cadrage de la communication vers le client
5. Arbitrages managériaux à trancher en interne
6. Liste des actions de réaction immédiate
7. Plan de gestion de crise sur 72 heures
8. Opportunité et niveau d'escalade hiérarchique
```

---

## Livrable attendu de l'IA (Expected Output)

Exemple illustratif de la restitution attendue. Les résultats réels varient selon le modèle et les données injectées.

---

### 1. Ségrégation stricte des faits avérés et des conjectures

**Faits matériellement constatés :**
- Défaillance bloquante du module de paiement sous conditions précises
- Reproductibilité validée sur staging et dev
- Constat survenu à J-3 de la mise en production
- Communication de lancement déjà lancée en interne par le client
- Escalade verbale effectuée auprès de la direction de projet interne

**Inconnues et conjectures (non vérifiées) :**
- Cause racine du bug
- Étendue des impacts collatéraux sur l'application
- Charge nécessaire au développement et au déploiement du correctif
- Antériorité de l'anomalie sur le référentiel de code
- Viabilité du maintien de la livraison Vendredi avec campagne de tests complète

---

### 2. Cartographie du périmètre d'impact

| Périmètre | Impact constaté ou potentiel | État des lieux |
|---|---|---|
| Module de paiement | Erreur bloquante sous conditions particulières | Confirmé (reproductibilité avérée) |
| Modules adjacents | Risque d'effets de bord inconnu | Analyse en cours |
| Calendrier de déploiement | Menace directe de report de livraison | Subordonné au chiffrage du correctif |
| Communication client | Impact organisationnel et d'image fort en cas de report | Risque critique avéré |

---

### 3. Vérifications impératives à mener avant la fin de la journée (J0)

- [ ] Isoler précisément les paramètres de déclenchement (jeux de données et parcours utilisateur exacts)
- [ ] Conclure le diagnostic d'impact sur les modules tiers
- [ ] Obtenir une estimation rigoureuse du temps de correction technique (scénario nominal vs scénario dégradé)
- [ ] Évaluer la durée incompressible de rejeu de la recette après correctif

---

### 4. Éléments de cadrage de la communication vers le client

> **Avertissement :** Le contenu, le timing et la posture diplomatique vis-à-vis du client relèvent d'un arbitrage managérial strict prenant en compte le contrat et la relation commerciale. Ne reprenez pas le texte de l'IA sans filtre.

**Principes de communication (matrice de base) :**
- Transparence sur le fait qu'une anomalie d'homologation fait l'objet d'investigations actives
- Présenter le dispositif de diagnostic mobilisé sans formuler d'engagements calendaires prématurés
- Rassurer sur le fait que la décision ferme sur le calendrier sera communiquée dès qualification de l'impact
- S'en tenir exclusivement aux faits constatés sans propager d'hypothèses anxiogènes

**Timing de notification :**
- Idéalement dès que le temps de correction et l'impact sur le calendrier sont chiffrés
- Toutefois, compte tenu de la communication interne déjà déployée par le client, envisager un pré-avis d'investigation sans délai si le report devient probable

---

### 5. Arbitrages managériaux à trancher en interne

- Seuil de décision de report : déterminer l'heure limite (ex. Mercredi 12h) au-delà de laquelle l'absence de correctif fiable impose formellement l'annulation du déploiement de Vendredi
- Validation de la gouvernance de crise et approbation du plan de communication client
- Priorisation absolue des ressources techniques affectées à la résolution
- Scénarios de repli : déploiement partiel (gel temporaire de l'option de paiement incriminée) ou report intégral de la version

---

### 6. Liste des actions de réaction immédiate

| # | Action opérationnelle | Responsable | Échéance |
|---|---|---|---|
| 1 | Qualification des conditions de reproduction et des modules collatéraux | Développeur référent | Ce soir |
| 2 | Chiffrage de l'effort de correction et calendrier de test | Lead Tech | Ce soir |
| 3 | Point de situation formalisé avec la direction interne | Chef de Projet | Ce soir |
| 4 | Arbitrage de la posture de communication client | Chef de Projet / Direction | Ce soir |
| 5 | Prise de contact avec le Contact client A selon la stratégie retenue | Chef de Projet | Après validation interne |

---

### 7. Plan de gestion de crise sur 72 heures

| Phase | Objectifs et livrables opérationnels |
|---|---|
| **Jour 1 (Ce jour)** | Identification de la cause, isolation du bug, évaluation de l'effort, alignement de la gouvernance interne |
| **Jour 2 (J-2)** | Développement du correctif, communication formelle de situation au client, décision collégiale Go/No-Go pour la date cible |
| **Jour 3 (J-1)** | Déploiement du correctif sur staging, exécution complète des tests de non-régression, arbitrage final de mise en prod |

---

### 8. Opportunité et niveau d'escalade hiérarchique

**Escalade managériale indispensable :**
- Le décalage éventuel de la livraison finale excède les prérogatives du chef de projet et requiert l'aval de la direction
- L'impact d'image chez le client commande une couverture par les instances de gouvernance du compte
- Le choix entre un report global ou une livraison en mode dégradé doit être arbitré collégialement

---

## Points de contrôle humain (Human Review Points)

Avant toute action sur le terrain, le chef de projet doit analyser :

- Si la frontière entre faits mesurés et suppositions techniques reflète exactement le niveau d'investigation
- Si la temporalité de l'annonce au client préserve la confiance sans créer de panique prématurée
- Si les capacités réelles de mobilisation technique permettent de tenir le plan sur 72 heures sans épuisement des équipes
- Si les clauses contractuelles prévoient des pénalités ou des protocoles formels de notification d'incident
- L'interdiction absolue de transmettre les préconisations brutes de l'IA au client sans réécriture humaine

---

## Consignes de sécurité et avertissements (Caution)

> [!IMPORTANT]
> Ce scénario est intégralement fictif.
>
> Ne saisissez jamais de détails techniques réels non anonymisés, d'identifiants ou d'informations confidentielles dans un moteur d'IA.
>
> **L'IA ne prend pas les décisions de crise.** Les décisions de maintien, d'annulation ou de bascule de production relèvent de la responsabilité légale et opérationnelle de l'encadrement humain.
