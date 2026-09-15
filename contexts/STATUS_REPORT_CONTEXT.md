# Contexte de rapport d'avancement / Status Report Context

---

## Purpose (Objectif de ce contexte)

Ce contexte structure et accélère la rédaction des rapports d'avancement de projet (Status Reports) assistée par IA.

Il permet d'adapter la tonalité, le niveau de granularité et les éléments de langage selon les publics cibles : communication interne (équipe/management), reporting client ou note de synthèse pour la direction.

**Les sorties générées constituent des projets de travail.** Ne diffusez jamais ces rapports sans relecture, vérification factuelle et validation par un responsable humain.

---

## Use Case (Cas d'usage)

- Rédiger les rapports d'avancement hebdomadaires ou mensuels.
- Adapter les niveaux de discours entre le reporting interne et le compte rendu client.
- Expliciter diplomatiquement et factuellement les dérives calendaires, points de blocage et risques.
- Structurer les demandes d'arbitrage à soumettre au management.

---

## Input (Informations à fournir à l'IA)

Après avoir chargé ce contexte, transmettez les informations ci-dessous (veillez à anonymiser rigoureusement les données sensibles et nominatives) :

```
### Travaux achevés sur la période (Semaine/Mois)
-

### Tâches non finalisées (Reportées sur la période suivante)
-

### Tâches et chantiers en retard
- Nature du retard :
- Causes racines de la dérive :
- Périmètre d'impact :
- Plan de rattrapage / Actions correctives :

### Points de blocage (Issues)
- Description du blocage :
- Statut :
- Responsable (par rôle : Développeur A, Lead Tech, etc.) :
- Échéance de résolution :

### Registre des risques
- Description du risque :
- Mesures de contournement / Mitigation :

### Arbitrages et validations client en attente
-

### Prévisions pour la période suivante
-

### Cible du rapport
- Destinataires internes (Management / Équipe projet)
- Destinataires externes (Client)
- Autre :
```

---

## Output (Livrables attendus de l'IA)

### 1. Rapport d'avancement interne (Équipe & Management)
Format transparent intégrant l'intégralité des difficultés techniques, incidents ouverts, risques projet et besoins de soutien.

### 2. Rapport d'avancement client
Format orienté valeur et maîtrise, focalisé sur les réalisations tangibles, les livrables, les actions attendues du client et la trajectoire globale, sans étaler les péripéties internes.

### 3. Synthèse exécutive pour la Direction
Condensé percutant structuré en 4 points : Situation globale, Bloquants majeurs, Arbitrages sollicités, Prochaines actions.

### 4. Bilan des risques et plan de contingence
Section dédiée aux risques résiduels et aux mesures d'atténuation.

### 5. Dossier d'arbitrage
Exposé argumenté des questions soumises à la validation de la gouvernance.

### 6. Feuille de route immédiate (Next Actions)
Checklist opérationnelle des actions engagées pour la période suivante.

---

## Matrice de calibrage selon l'audience

| Destinataire | Ligne éditoriale & Posture |
|---|---|
| **Interne / Management** | Transparence totale : expliciter sans fard les blocages, dérives budgétaires/délais et besoins d'arbitrage |
| **Client** | Factualité, diplomatie et maîtrise : mettre en avant les réalisations, cadrer les impacts, expliciter les actions attendues du client sans imputer de fautes directes |
| **Équipe de réalisation** | Clarté opérationnelle : tâches, critères d'achèvement (DoD), échéances et porteurs d'action |
| **Comex / PMO** | Vision synthétique de haut niveau : météo du projet, jalons clés, alertes critiques et arbitrages stratégiques |

---

## Caution (Précautions d'usage)

> [!CAUTION]
> Ne transmettez jamais un rapport d'avancement généré par l'IA sans validation humaine préalable.
>
> Tout engagement sur le planning, les charges, la facturation ou le périmètre de responsabilité figurant dans un document client doit être formellement validé par le chef de projet.
>
> Ne saisissez aucun nom propre, raison sociale, donnée contractuelle ou identifiant technique dans les outils d'IA.

---

## Modèles de prompts standards

### 【Modèle complet】Production simultanée des formats Interne, Client et Direction

```text
# Demande de rédaction de rapport d'avancement (Status Report)

Sur la base des contextes de référence ci-dessous, rédigez le rapport d'avancement de la semaine selon les formats [Interne / Client / Direction].

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de STATUS_REPORT_CONTEXT.md]

---

## Données de la période (Données strictement anonymisées)

### Travaux achevés
-

### Travaux non finalisés
-

### Tâches en retard (avec causes et plan de rattrapage)
-

### Points de blocage (Issues)
-

### Risques
-

### Validations client en attente
-

### Prévisions pour la semaine prochaine
-

---

## Livrables attendus

1. Rapport d'avancement interne (avec blocages, risques et demandes d'arbitrage)
2. Rapport d'avancement client (synthèse valorisante des faits et prochaines échéances)
3. Synthèse exécutive pour la Direction (Situation, Alertes, Arbitrages, Actions)
4. Liste ordonnancée des prochaines actions

※ Tout livrable doit impérativement être relu et ajusté avant transmission.
※ Ne jamais envoyer la version client brute sans validation.
```

---

### 【Modèle Interne】Focus sur la transparence opérationnelle et les blocages

```text
Sur la base des contextes de référence ci-dessous, rédigez le rapport d'avancement interne hebdomadaire destiné à l'équipe et au management.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de STATUS_REPORT_CONTEXT.md]

---

## Données de la période (Données anonymisées)

### Travaux achevés
-

### Travaux reportés
-

### Tâches en retard (causes et contre-mesures)
-

### Points de blocage
-

### Risques
-

### Arbitrages sollicités
-

### Objectifs de la semaine prochaine
-

---

## Structure de restitution

- Réalisations de la semaine (listes à puces)
- Écarts et reports d'activité
- Tableau synthétique des blocages et risques
- Points d'arbitrage soumis au management
- Plan de charge et objectifs de la période suivante

※ Validation humaine obligatoire avant communication.
```

---

### 【Modèle Client】Focus sur la maîtrise, les livrables et la valeur

```text
Sur la base des contextes de référence ci-dessous, rédigez la communication d'avancement hebdomadaire destinée au client.
Adoptez une posture professionnelle et constructive en omettant les difficultés internes pour vous concentrer sur l'état d'avancement réel et les prérequis côté client.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de STATUS_REPORT_CONTEXT.md]

---

## Données de la période (Données anonymisées)

### Travaux achevés
-

### Travaux en cours
-

### Impacts et validations attendues du client
-

### Prochains jalons et livraisons prévus
-

---

## Structure de restitution

- Synthèse des réalisations franchies (perspective valeur client)
- État d'avancement des livrables
- Actions et validations requises de la part du client
- Calendrier directeur et priorités de la semaine suivante

※ Brouillon d'aide à la rédaction : ne pas diffuser au client sans relecture managériale.
※ Vérifier impérativement les formulations relatives aux délais, coûts et périmètre contractuel.
```

---

## Version structurée pour Claude (Format balises XML)

Pour une utilisation avec Claude, la structure balisée suivante garantit une parfaite distinction des registres de discours :

```text
<task>
Sur la base des données d'avancement ci-dessous, générez le rapport d'avancement décliné en version interne, client et synthèse direction.
Veillez à respecter scrupuleusement les nuances de langage et à expliciter les risques et arbitrages.
</task>
<context>
<pm_context>
[Coller ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Coller ici le contenu de STATUS_REPORT_CONTEXT.md]
</specific_context>
</context>
<input>
【Données de la période (Données strictement anonymisées)】

### Travaux achevés
-

### Travaux non finalisés
-

### Tâches en retard
- Nature du retard :
- Causes racines :
- Plan d'action :

### Points de blocage
-

### Risques
-

### Arbitrages client en attente
-

### Objectifs de la semaine suivante
-
</input>
<constraints>
- Considérez les données comme rigoureusement anonymisées (noms propres, entreprises et identifiants exclus).
- Mentionnez « (Hypothèse) » pour tout élément complété par déduction.
- Ne formulez aucun engagement ferme sur les délais, budgets ou responsabilités dans la version client.
- Les livrables constituent une base de travail soumise à validation humaine.
</constraints>
<output_format>
1. Rapport d'avancement interne (avec gestion des blocages, risques et arbitrages)
2. Rapport d'avancement client (orienté livrables, jalons et actions client)
3. Synthèse exécutive pour la Direction (Situation, Alertes, Arbitrages, Actions)
4. Tableau récapitulatif des risques
5. Liste des prochaines actions ordonnancées
</output_format>
```
