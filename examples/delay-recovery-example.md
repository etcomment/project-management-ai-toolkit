# Élaboration d'un plan de rattrapage en cas de retard (Delay Recovery) — Exemple pratique

## Cas d'usage (Use Case)

Ce scénario modélise une situation où des dérives de planning cumulées affectent à la fois le développement des interfaces et la phase de conception des tests.

L'objectif est d'exploiter l'IA pour objectiver les causes racines de la dérive, ségréguer le chemin critique, arbitrer entre crashing (renfort capacitaire) et fast-tracking (parallélisation / réduction de périmètre), et structurer la communication managériale et client.

---

## Fichiers de contexte utilisés

- `contexts/PM_CONTEXT.md`
- `contexts/DELAY_RECOVERY_CONTEXT.md`

---

## Données d'entrée anonymisées (Sanitized Input)

> **Avertissement :** Les données ci-dessous sont entièrement fictives. Aucun nom réel de client, de projet ou d'individu n'est mentionné.

```
Projet : Projet Alpha (Fictif)
Date de cadrage : Semaine 10 (S10)

【Chantiers en dérive / retard constaté】
1. Module d'interfaces externes (développement et tests unitaires) : 1,5 semaine de retard par rapport à la baseline
2. Élaboration du plan de conception des tests : démarrage effectif décalé d'une semaine, actuellement en cours de rédaction

【Causes racines de la dérive】
1. Flux externes : immobilisation du développement dans l'attente d'arbitrages de spécifications par le client (désormais stabilisées)
2. Conception des tests : retard dans l'affectation nominative du rédacteur dédié

【Volume de retard et effort d'absorption】
- Résorption de la dérive des flux externes : nécessite a minima 1 semaine pleine d'effort focalisé
- Plan de tests : en cours, finalisation estimée avec 3 à 4 jours de retard sur le calendrier théorique

【Restes à faire (Work Remaining)】
- Flux externes : tests unitaires, cadrage de l'interfaçage avec le partenaire tiers, déroulement des tests d'intégration
- Plan de tests : en cours de finalisation (échéance cible : fin de semaine)
- Tests d'intégration : non démarrés (conditionnés par la livraison du plan de tests)
- Recette usine / pré-recette client : non démarrée
- Comité de validation Go/No-Go : date toujours non fixée

【Chemin critique (Critical Path)】
Achèvement des flux externes → Tests d'intégration → Recette / Homologation → Comité Go/No-Go de mise en prod

【Capacité opérationnelle disponible】
- Développeur référent : mobilisé à 100% sur les flux externes
- Équipe de test : disponible et mobilisable immédiatement dès stabilisation du plan de tests
- Renfort externe ponctuel : envisageable mais requiert un délai de mise à disposition de plusieurs jours ouvrés

【Contraintes de délai non négociables】
- Délai résiduel avant mise en production : 3,5 semaines (échéance ferme communiquée en interne par le client)
- Date du comité Go/No-Go toujours indéterminée

【Impacts et relation client】
- Le client organise ses déploiements internes sur la base du calendrier initial
- Le niveau de retard opérationnel n'a pas encore fait l'objet d'une notification formelle au Contact client A

【Mesures conservatoires d'ores et déjà engagées】
- Spécifications des flux externes définitivement validées la semaine passée
- Rédacteur du plan de tests affecté et à la tâche depuis ce début de semaine
- Focalisation exclusive du développeur principal sur la finalisation du code
```

---

## Prompt

```text
Après avoir intégré les fichiers de contexte ci-dessous, élabore une stratégie rigoureuse de rattrapage de retard projet (Delay Recovery).

【Fichiers de contexte】
- contexts/PM_CONTEXT.md
- contexts/DELAY_RECOVERY_CONTEXT.md

【Données de situation】
(Coller les données d'entrée anonymisées ci-dessus)

Structure ton analyse selon les axes suivants :
1. Diagnostic des causes de la dérive
2. Cartographie des impacts sur le chemin critique
3. Scénarios alternatifs de rattrapage (Options A, B, C)
4. Matrice de priorisation opérationnelle
5. Pistes d'élagage ou de simplification de tâches non critiques
6. Besoins de renforts ou d'assistance externe
7. Trame de communication et de négociation avec le client
8. Plan d'escalade hiérarchique interne
9. Plan d'intervention immédiat pour les 24 à 72 prochaines heures
```

---

## Livrable attendu de l'IA (Expected Output)

Exemple illustratif de la restitution attendue. Les résultats réels varient selon le modèle et les données injectées.

---

### 1. Diagnostic des causes de la dérive

| Tâche en retard | Cause racine principale | Situation actuelle |
|---|---|---|
| Module flux externes | Blocage exogène consécutif à l'attente de validation client | Spécifications actées. Développement et tests en cours d'exécution active |
| Plan de tests | Défaillance d'affectation interne des ressources | Rédacteur mobilisé. Livraison attendue en fin de semaine courante |

Le retard résulte de la conjonction d'un facteur externe (attente d'arbitrage client) et d'un facteur interne de gouvernance (latence de staffing).

---

### 2. Cartographie des impacts sur le chemin critique

| Étape du cycle | Conséquence opérationnelle |
|---|---|
| Démarrage des tests d'intégration | Bloqué par l'achèvement des flux externes. L'équipe de test ne pourra démarrer dès la remise du plan de tests |
| Fenêtre de recette client | Le glissement des tests d'intégration rogne directement sur le temps imparti pour l'homologation |
| Comité Go/No-Go | L'absence de date ferme empêche tout rétroplanning rigoureux et toute mobilisation des décideurs |
| Jalon final de déploiement | En l'absence de compression du cycle aval, l'échéance des 3,5 semaines ne pourra être tenue |

---

### 3. Scénarios alternatifs de rattrapage

**Scénario A : Concentration maximale sur le chemin critique (Recommandé)**
- Finaliser le socle et les tests unitaires des flux externes d'ici la fin de semaine pour enclencher les tests d'intégration dès la semaine 11
- Hiérarchiser la couverture de test sur les fonctionnalités vitales (P1) pour absorber le décalage sans allonger la durée globale
- Risque : couverture allégée sur les cas d'usage secondaires

**Scénario B : Renfort de ressources (Crashing)**
- Injecter un développeur d'appui pour paralléliser la finalisation des flux et la préparation des jeux d'essais
- Risque : temps d'onboarding incompressible réduisant l'efficacité immédiate sur une fenêtre de 3,5 semaines

**Scénario C : Réajustement de périmètre en concertation avec le client (Scope Descoping)**
- Geler temporairement les connecteurs secondaires pour une v1.1 post-lancement et livrer le cœur nominal à la date convenue
- Risque : nécessite un accord politique et formel immédiat du client

---

### 4. Matrice de priorisation opérationnelle

| Priorité | Chantier | Justification opérationnelle |
|---|---|---|
| **P1 - Critique** | Achèvement du code et des tests unitaires des flux externes | Sur le chemin critique absolu. Tout jour perdu bloque les étapes de qualification |
| **P2 - Haute** | Finalisation et revue du plan de tests | Conditionne l'exécution rigoureuse de la recette d'intégration |
| **P2 - Haute** | Verrouillage de la date du comité Go/No-Go | Nécessaire pour piloter le compte à rebours de livraison |
| **P3 - Moyenne** | Calage d'agenda avec le partenaire externe | Dépend de la disponibilité de tiers, à déclencher sans délai |

---

### 5. Pistes d'élagage ou de simplification de tâches non critiques

> **Avertissement :** Toute simplification de périmètre ou de test induit un risque résiduel sur la qualité. L'arbitrage final relève de la direction de projet.

- Réduire le niveau de granularité des cas de tests sur les parcours administratifs secondaires non critiques
- Focaliser la recette client sur les parcours utilisateurs nominaux validants pour accélérer l'homologation
- Reporter le traitement des anomalies mineures d'affichage (P3/P4) à un patch post-mise en production

---

### 6. Besoins de renforts ou d'assistance externe

- **Recette avec le système externe** : Réserver impérativement les créneaux de l'interlocuteur technique tiers (Contact B) pour éviter une attente stérile
- **Exécution des tests** : Préparer l'environnement de recette pour que les testeurs soient opérationnels à la minute où le code des flux est livré
- **Option Renfort (Scénario B)** : L'arbitrage de mobilisation doit intervenir sous 48h maximum sous peine d'être inopérant

---

### 7. Trame de communication et de négociation avec le client

> **Avertissement :** La posture et les éléments communiqués au client doivent être validés en amont avec votre direction.

**Axe de communication managériale :**
- Rappeler la relance opérationnelle consécutive à la validation récente des spécifications
- Démontrer la mise en place d'un dispositif d'accélération focalisé pour sécuriser la mise en production
- Présenter les options de cadrage (notamment la priorisation des tests clés) garantissant l'intégrité de la date cible
- Solliciter le calage sans délai de la date du comité décisionnel de mise en production

---

### 8. Plan d'escalade hiérarchique interne

- Présentation immédiate d'un point de situation formalisé à la direction de projet
- Soumission pour arbitrage du choix entre le Scénario A (priorisation des tests) et le Scénario C (arbitrage de périmètre)
- Cadrage avec la direction commerciale en cas de négociation contractuelle avec le client

---

### 9. Plan d'intervention immédiat pour les 24 à 72 prochaines heures

| Échéance | Actions d'urgence |
|---|---|
| **Dans les 24h** | Revue d'avancement au micron avec le dev sur les flux externes ; confirmation de la date butoir de livraison |
| **Dans les 48h** | Contrôle de la finalisation du plan de tests ; envoi de la demande officielle de fixation du comité Go/No-Go au client |
| **Sous 72h** | Calage formel des créneaux de tests partenaires ; arbitrage hiérarchique sur l'activation d'un renfort ou d'une réduction de périmètre ; point de cadrage avec le client |

---

## Points de contrôle humain (Human Review Points)

Préalablement à tout arbitrage opérationnel, le chef de projet doit contrôler :

- La faisabilité technique réelle du Scénario A auprès des équipes de développement et de qualification
- L'acceptabilité juridique et contractuelle d'une réduction de couverture de test
- L'alignement du discours de transparence avec les enjeux commerciaux et politiques du compte
- La stricte conformité des propositions d'escalade avec l'organigramme de gouvernance interne
- Le caractère réaliste du calendrier des 72 prochaines heures au regard de la disponibilité effective des acteurs

---

## Consignes de sécurité et avertissements (Caution)

> [!IMPORTANT]
> Ce scénario est intégralement fictif.
>
> Anonymisez scrupuleusement toutes vos données projet avant utilisation d'une IA générative.
>
> **L'IA ne prend pas de décisions d'engagement calendaire ou contractuel.** Tout arbitrage de délai, de budget ou de périmètre relève de la seule responsabilité des décideurs humains de l'organisation.
