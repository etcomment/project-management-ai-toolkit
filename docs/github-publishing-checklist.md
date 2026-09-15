# Checklist de publication GitHub / GitHub Publishing Checklist

Cette checklist réunit l'ensemble des points de contrôle à valider avant de rendre ce dépôt public ou d'en assurer la communication officielle.

---

## Finalité de ce document

Ce document vise à prévenir toute omission de paramétrage, fuite d'informations sensibles ou non-respect de la ligne éditoriale lors de la publication du dépôt sur GitHub.

Suivez méthodiquement ces étapes depuis la préparation technique jusqu'au lancement de la communication.

---

## Processus de mise en ligne

```text
Préparation de la publication GitHub
│
├─ Vérification du rendu du README
├─ Configuration du champ Description
├─ Configuration du lien Website
├─ Définition des Topics (tags)
├─ Configuration de l'image Social Preview (OGP)
├─ Vérification des templates d'Issues et de PR
├─ Contrôle d'absence de données confidentielles
└─ Validation des supports de communication
```

---

## Éléments à configurer sur l'interface GitHub

Ces paramètres se configurent depuis la page d'accueil du dépôt GitHub, via l'icône d'engrenage de la section « About » (en haut à droite) :

### About / Description
Description concise du dépôt, affichée dans les résultats de recherche et lors des partages sur les réseaux sociaux.

### Website
URL du site officiel de référence ou de la page de présentation de la boîte à outils.

### Topics (Tags)
Mots-clés thématiques favorisant l'indexation et la découvrabilité sur GitHub.

### Social Preview
Image Open Graph (OGP) affichée lors du partage du lien du dépôt sur les réseaux sociaux ou messageries.

### Pin repository (Épinglage)
Épingler le dépôt sur le profil de l'organisation ou de l'utilisateur pour maximiser sa visibilité.

### Contrôle du rendu du README
Vérifier la lisibilité, le bon formatage des tableaux et la validité des liens sur la page d'accueil du dépôt.

---

## Recommandations pour le champ Description

Version anglaise (recommandée pour la visibilité internationale) :

```text
AI context files, usage examples, and Claude Code skills for PMs/PMOs. Supports ChatGPT, Gemini, Claude, and Claude Code.
```

Version française :

```text
Boîte à outils IA pour chefs de projet et PMO compatible ChatGPT, Gemini, Claude et Claude Code. Inclut contextes IA, compétences Claude Code et cas réels.
```

---

## Recommandation pour le champ Website

```text
https://techaide.jp/
```

---

## Topics (Tags) recommandés

```text
project-management
pmo
pm
chatgpt
gemini
claude
claude-code
ai-context
prompt-engineering
engineering-management
french
```

---

## Image d'aperçu pour les réseaux sociaux (Social Preview)

Image OGP s'affichant lors du partage du dépôt sur GitHub, X (Twitter), LinkedIn, Slack, etc. :

- Améliore considérablement le taux de clic et la visibilité des partages.
- Privilégier un graphisme épuré avec des textes courts et percutants.
- Faire figurer le nom du dépôt et son sous-titre de positionnement.
- Ne faire figurer aucune donnée confidentielle, nom propre ou secret technique.
- Si le fichier `assets/social-preview.svg` est présent, utilisez-le comme base graphique.
- Convertir en format PNG pour téléversement dans les paramètres GitHub.

Emplacement : Settings > General > Social preview sur GitHub.

---

## Contrôles impératifs avant publication publique

Avant de basculer le dépôt en visibilité publique, validez les points suivants :

- [ ] Le rendu du README.md est impeccable et sans rupture de mise en page
- [ ] Aucun répertoire `prompts/` n'a été recréé (les exemples restent intégrés dans chaque contexte)
- [ ] Le répertoire `contexts/` est clairement identifié comme le composant central
- [ ] Les mentions de non-responsabilité et les consignes de sécurité IA sont bien présentes
- [ ] Les modèles d'Issues et de Pull Requests sont configurés et fonctionnels
- [ ] Aucun script exécutable non contrôlé n'a été introduit
- [ ] Aucune clé d'API, mot de passe, token ou certificat n'est présent dans l'historique git
- [ ] Aucun nom de client réel, raison sociale, nom de collaborateur ou projet confidentiel ne subsiste
- [ ] Les compétences Claude Code ne comportent aucun hook, commande CLI, configuration MCP ou déclenchement automatique
- [ ] Les liens promotionnels vers les formations restent mesurés et pertinents

---

## Contrôles préalables avant communication externe

Avant toute annonce sur les réseaux sociaux, blogs ou plateformes professionnelles :

- [ ] La section About de GitHub est dûment complétée
- [ ] Le lien Website pointe vers la bonne URL
- [ ] Les Topics sont renseignés
- [ ] L'image Social Preview est active et s'affiche correctement
- [ ] L'en-tête du README explicite immédiatement la finalité de la boîte à outils
- [ ] Les articles de présentation ou posts de lancement rappellent clairement les limites opérationnelles de l'IA et la clause de non-responsabilité
