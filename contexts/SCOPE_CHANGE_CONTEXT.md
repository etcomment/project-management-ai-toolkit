# Contexte de gestion des changements de périmètre / Scope Change Context

---

## Purpose (Objectif de ce contexte)

Ce contexte permet d'analyser et de cadrer les évolutions de spécifications, demandes de changement de périmètre (Change Requests) et demandes d'ajouts fonctionnels. Il apporte une aide méthodologique pour objectiver les écarts par rapport au périmètre initial, qualifier les impacts (charges, délais, coûts, adhérences techniques) et identifier les arbitrages indispensables.

**L'IA ne remplace pas l'arbitrage du chef de projet.** L'IA est un outil de structuration et d'instruction des points d'arbitrage. Les engagements fermes et les arbitrages contractuels relèvent impérativement de la responsabilité humaine.

> [!CAUTION]
> Ne saisissez jamais de montants financiers contractuels, de chiffrages de devis fermes ou de clauses de responsabilité juridique dans les outils d'IA.
> N'introduisez aucun nom de client, raison sociale, nom de collaborateur ou clé d'authentification.

---

## Use Case (Cas d'usage)

- Structurer l'analyse d'impact d'une demande d'évolution ou d'un changement de spécifications client.
- Matérialiser précisément l'écart (delta) entre le périmètre contractuel initial (baseline) et la nouvelle demande.
- Évaluer les répercussions prévisibles sur la charge (J/H), les jalons de livraison et le budget.
- Identifier la liste des questions et clarifications indispensables à soumettre au client.
- Bâtir des scénarios d'arbitrage contrastés (avec avantages et inconvénients) à soumettre aux comités de pilotage ou à la direction.

---

## Input (Informations à fournir à l'IA)

Après avoir chargé ce contexte, transmettez les informations ci-dessous (veillez à anonymiser rigoureusement les données confidentielles et nominatives) :

```
### Demande de changement / Expression du besoin
(Description synthétique du changement sollicité par le client ou les parties prenantes)

### Contexte et justification du changement
(Motivations métier, contraintes réglementaires ou opportunités à l'origine de la demande)

### Périmètre initial de référence (Baseline)
(Périmètre fonctionnel initialement contractualisé et convenu)

### Travaux supplémentaires induits
(Nouvelles tâches techniques ou fonctionnelles générées par cette évolution)

### Modules et fonctionnalités impactés
(Adhérences techniques, composants d'architecture ou processus métier affectés)

### Contraintes calendaires / Échéances
(Date d'effet souhaitée, jalon de livraison cible et flexibilité du calendrier)

### Contraintes budgétaires
(Cadre budgétaire d'ensemble ou contraintes de coûts identifiées)

### Points à clarifier avec le client
(Questions ouvertes et hypothèses nécessitant une validation formelle du client)
```

---

## Output (Livrables attendus de l'IA)

### 1. Synthèse de la demande de changement
Formalisation claire et synthétique du besoin exprimé et de sa portée.

### 2. Matrice d'écart avec le périmètre initial (Delta d'engagement)
Tableau comparatif entre la référence contractuelle initiale et la demande révisée.

### 3. Matrice d'impact fonctionnel et technique
Cartographie des modules, interfaces, flux et lots de travaux affectés par l'évolution.

### 4. Estimation d'impact sur les charges de réalisation
Qualification de la charge prévisible (chiffrage d'effort préliminaire, zones d'incertitude et besoins d'expertise).

### 5. Analyse d'impact sur le chemin critique et les délais
Évaluation des dérives calendaires potentielles et identification des jalons nécessitant un réordonnancement.

### 6. Impacts économiques et modèles de facturation
Identification des postes générateurs de surcoûts (sans formuler de chiffrage financier définitif).

### 7. Demandes de clarification pour le Client
Liste exhaustive des arbitrages et réponses techniques/fonctionnelles attendus du client avant tout engagement.

### 8. Scénarios d'arbitrage opérationnels
Propositions d'options (ex. : intégration au forfait avec décalage de date, dépriorisation d'autres fonctionnalités, report en phase ultérieure/V2) avec bilan bénéfices/risques.

### 9. Opportunité d'escalade managériale
Identification des points de tension justifiant la saisine du directeur de projet, de la direction commerciale ou du département juridique.

---

## Caution (Précautions d'usage)

- **Interdiction formelle d'engager la société sur les délais, les prix ou le périmètre sur la seule base des sorties de l'IA.** Ces éléments doivent impérativement être validés par le chef de projet, la direction commerciale et la direction de production.
- Les propositions d'avenants, devis complémentaires ou notifications de replanification destinés au client doivent être relus, modifiés et approuvés par un responsable qualifié.
- Ne renseignez aucun nom propre de client, d'entreprise ou de clauses contractuelles confidentielles.
- **Les livrables de l'IA ne valent pas avenant contractuel.**

---

## Modèle de prompt standard

Copiez ce modèle, renseignez les informations du changement de périmètre et soumettez la requête :

```text
Sur la base des contextes de référence ci-dessous, instruisez cette demande de changement de périmètre / de spécifications selon une perspective Chef de Projet.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de SCOPE_CHANGE_CONTEXT.md]

---

## Fiche de changement de périmètre (Données anonymisées)

### Demande de changement
(Renseigner)

### Contexte et justification du changement
(Renseigner)

### Périmètre initial de référence
(Renseigner)

### Travaux supplémentaires induits
(Renseigner)

### Modules et fonctionnalités impactés
(Renseigner)

### Contraintes calendaires
(Renseigner)

### Contraintes budgétaires
(Renseigner)

### Points à clarifier avec le client
(Renseigner)

---

## Livrables attendus

1. Synthèse de la demande de changement
2. Matrice d'écart avec le périmètre initial
3. Matrice d'impact fonctionnel et technique
4. Estimation d'impact sur les charges (J/H)
5. Analyse d'impact sur le chemin critique et les délais
6. Postes de coûts et impacts économiques induits
7. Demandes de clarification pour le client
8. Scénarios d'arbitrage et bilan bénéfices/risques
9. Éléments nécessitant une escalade managériale ou commerciale

※ L'arbitrage final sur les délais, le coût et le périmètre contractuel relève exclusivement de la responsabilité humaine.
※ Les sorties de l'IA constituent une base d'instruction interne qui doit être validée avant toute communication externe.
```

---

## Version structurée pour Claude (Format balises XML)

Pour une utilisation avec Claude, la structure balisée suivante assure une instruction méthodique :

```text
<task>
Pour la demande d'évolution ou de changement de périmètre ci-dessous, qualifiez le périmètre d'impact, les charges prévisibles, les incidences calendaires et budgétaires, formulez les scénarios d'arbitrage et identifiez les besoins d'escalade.
</task>
<context>
<pm_context>
[Coller ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Coller ici le contenu de SCOPE_CHANGE_CONTEXT.md]
</specific_context>
</context>
<input>
【Fiche de changement de périmètre (Données anonymisées)】

### Demande de changement
(Renseigner)

### Contexte et justification du changement
(Renseigner)

### Périmètre initial de référence
(Renseigner)

### Travaux supplémentaires induits
(Renseigner)

### Modules et fonctionnalités impactés
(Renseigner)

### Contraintes calendaires
(Renseigner)

### Points à clarifier avec le client
(Renseigner)
</input>
<constraints>
- Considérez les données fournies comme rigoureusement anonymisées (exclure tout nom propre ou élément d'identification).
- Ne saisissez aucun montant de contrat ou engagement contractuel ferme.
- Ne formulez pas d'estimation de charge comme une certitude absolue ; mentionnez « impacts prévisibles soumis à confirmation technique ».
- Formulez les réponses sous forme d'aide à la décision, l'arbitrage final revenant au responsable humain.
</constraints>
<output_format>
1. Synthèse de la demande de changement
2. Matrice d'écart avec le périmètre initial
3. Matrice d'impact fonctionnel et technique
4. Estimation d'impact sur les charges (avec mention des incertitudes)
5. Points de vigilance sur le respect des délais
6. Postes générateurs de surcoûts
7. Demandes de clarification pour le client
8. Scénarios d'arbitrage et balance avantages/inconvénients
9. Points nécessitant un arbitrage hiérarchique ou contractuel
</output_format>
```
