# Contexte de communication et reporting aux parties prenantes / Stakeholder Report Context

---

## Purpose (Objectif de ce contexte)

Ce contexte structure le reporting stratégique et opérationnel destiné aux parties prenantes clés : direction de département, comité de direction (Comex/Codir), directeurs de compte, référents côté client et PMO. Il fournit un cadre pour élaborer des synthèses exécutives percutantes, formaliser les points d'arbitrage et cadrer les demandes formelles de décision ou de soutien.

**L'IA ne remplace pas l'arbitrage du chef de projet.** L'IA est un outil de structuration et de formalisation d'aide à la décision. La validation finale relève impérativement de la responsabilité humaine.

> [!CAUTION]
> Ne transmettez aucun nom de client, raison sociale, identifiant de connexion ou élément contractuel confidentiel aux outils d'IA.
> Ne diffusez jamais directement une note de cadrage stratégique ou un dossier de décision généré par l'IA sans relecture, vérification et validation préalable par un responsable qualifié.

---

## Use Case (Cas d'usage)

- Préparer un flash report exécutif pour le management ou la direction générale.
- Formuler une demande formelle d'arbitrage ou de décision stratégique à soumettre aux décideurs.
- Structurer l'ordre du jour et la note de cadrage pour un comité de pilotage (Copil) client.
- Cadrer les éléments d'alerte et de reporting destinés au PMO.
- Formaliser une demande d'appui, de déblocage de ressources ou un dossier d'escalade.

---

## Input (Informations à fournir à l'IA)

Après avoir chargé ce contexte, transmettez les informations ci-dessous (veillez à anonymiser rigoureusement les données confidentielles et nominatives) :

```
### Profil des destinataires / Instance de reporting
(ex. : Directeur de pôle, Comité de direction, Directeur de projet client, PMO)

### Situation synthétique du projet
(Phase actuelle, niveau d'avancement global et dynamique générale du projet)

### Points de blocage et alertes critiques (Issues)
(Incidents majeurs actuels ou difficultés émergentes nécessitant une visibilité)

### Registre des risques majeurs
(Risques avérés et risques latents pesant sur les objectifs du projet)

### Points nécessitant un arbitrage ou une décision
(Décisions opérationnelles, contractuelles ou budgétaires à trancher par l'instance)

### Demandes d'appui ou d'intervention
(Actions de soutien, déblocage de moyens ou interventions managériales attendues)

### Échéance de communication
(Date et heure de restitution ou de diffusion du reporting)

### Trajectoire et plan d'action PM
(Mesures déjà engagées et orientations prévues par l'équipe projet d'ici la prochaine échéance)
```

---

## Output (Livrables attendus de l'IA)

### 1. Synthèse exécutive (Executive Summary)
Flash report de haut niveau permettant aux décideurs d'appréhender la situation en 1 à 2 minutes (3 à 5 lignes percutantes).

### 2. État d'avancement et situation opérationnelle
Synthèse objective du franchissement des jalons, de la tenue du planning et de la dynamique globale.

### 3. Principaux points d'attention (Focus thématique)
Explicitation des blocages critiques, de leurs causes profondes et de leurs répercussions concrètes.

### 4. Dossier de décision et points d'arbitrage
Formulation précise des options d'arbitrage soumises à la validation formelle des parties prenantes.

### 5. Demande formelle de soutien
Expression claire des leviers managériaux ou organisationnels sollicités auprès de l'instance.

### 6. Cartographie des risques et mesures d'atténuation
Tableau de synthèse des risques résiduels et stratégie de maîtrise portée par le chef de projet.

### 7. Feuille de route d'ici le prochain point d'étape
Liste des engagements et actions opérationnelles pris par le chef de projet pour la période à venir.

---

## Caution (Précautions d'usage)

- **Ne transmettez jamais de communication exécutive issue de l'IA sans validation humaine.** Toute communication destinée au management ou aux décideurs clients doit être rigoureusement revue et ajustée.
- Ne renseignez aucun nom propre de client, d'entreprise ou de données personnelles.
- N'introduisez aucun élément contractuel ou financier confidentiel.
- Pesez rigoureusement les termes touchant aux engagements de délais, de coûts ou de responsabilités.
- **Les livrables de l'IA constituent une aide à la préparation et non une décision managériale.**

---

## Modèle de prompt standard

Copiez ce modèle, renseignez les éléments de situation et soumettez la requête :

```text
Sur la base des contextes de référence ci-dessous, préparez une note de reporting stratégique destinée aux parties prenantes selon une perspective Chef de Projet.

## Contextes

[Coller ici le contenu de PM_CONTEXT.md]
[Coller ici le contenu de STAKEHOLDER_REPORT_CONTEXT.md]

---

## Données de reporting (Données strictement anonymisées)

### Profil des destinataires
(Renseigner)

### Situation synthétique du projet
(Renseigner)

### Points de blocage et alertes critiques
(Renseigner)

### Registre des risques majeurs
(Renseigner)

### Points nécessitant un arbitrage ou une décision
(Renseigner)

### Demandes d'appui ou d'intervention
(Renseigner)

### Échéance de communication
(Renseigner)

### Trajectoire et plan d'action PM
(Renseigner)

---

## Livrables attendus

1. Synthèse exécutive (Executive Summary - 3 à 5 lignes)
2. État d'avancement et situation opérationnelle
3. Principaux points d'attention (blocages, causes, impacts)
4. Dossier de décision et points d'arbitrage
5. Demande formelle de soutien
6. Cartographie des risques et mesures d'atténuation
7. Feuille de route d'ici le prochain point d'étape

※ Toute communication destinée à la gouvernance requiert une validation humaine préalable.
※ Les sorties constituent une base de travail : l'arbitrage final relève exclusivement de la responsabilité humaine.
```

---

## Version structurée pour Claude (Format balises XML)

Pour une utilisation avec Claude, la structure balisée suivante garantit une restitution calibrée :

```text
<task>
Sur la base des éléments projet ci-dessous, préparez la note de communication destinée aux parties prenantes : synthèse exécutive, analyse des points clés, arbitrages requis, demandes d'appui et prochaines actions.
</task>
<context>
<pm_context>
[Coller ici le contenu de PM_CONTEXT.md]
</pm_context>
<specific_context>
[Coller ici le contenu de STAKEHOLDER_REPORT_CONTEXT.md]
</specific_context>
</context>
<input>
【Données de reporting (Données strictement anonymisées)】

### Profil des destinataires
(Renseigner)

### Situation synthétique du projet
(Renseigner)

### Points de blocage et alertes critiques
(Renseigner)

### Registre des risques majeurs
(Renseigner)

### Points nécessitant un arbitrage ou une décision
(Renseigner)

### Demandes d'appui ou d'intervention
(Renseigner)

### Trajectoire et plan d'action PM
(Renseigner)
</input>
<constraints>
- Considérez les données fournies comme rigoureusement anonymisées (exclure tout nom propre ou élément d'identification).
- Si vous complétez des informations manquantes, mentionnez expressément « (Hypothèse) ».
- Ne formulez aucune affirmation péremptoire sur des questions de droit, de budget contractuel ou de responsabilité juridique.
- Précisez que la note doit obligatoirement faire l'objet d'une validation humaine avant diffusion aux décideurs.
</constraints>
<output_format>
1. Synthèse exécutive (3 à 5 lignes)
2. État d'avancement et situation opérationnelle
3. Principaux points d'attention (blocages, causes, impacts)
4. Dossier de décision et points d'arbitrage
5. Demande formelle de soutien
6. Cartographie des risques et mesures d'atténuation
7. Feuille de route d'ici le prochain point d'étape
</output_format>
```
