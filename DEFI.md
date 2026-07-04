[DEFI.md](https://github.com/user-attachments/files/29659904/DEFI.md)
# DEFI.md

### Nom du défi
MANUEL — Outil d'analyse de recevabilité des amendements parlementaires

### Description courte
Un add-in Microsoft Word qui analyse instantanément la recevabilité constitutionnelle d'un amendement (articles 40, 41 et 45 de la Constitution), détecte les risques de cavalier législatif, d'irrecevabilité financière et d'empiètement sur le domaine réglementaire — 100 % local, sans IA, sans serveur.

### Porteur
Lou-Anne Lombart

### Description longue
**Contexte**

Chaque semaine, des centaines d'amendements sont déposés à l'Assemblée nationale. Une part non négligeable est déclarée irrecevable pour des motifs constitutionnels — article 45 (cavalier législatif), article 40 (charge financière sans gage), article 41 (empiètement sur le domaine réglementaire) — qui auraient pu être détectés en amont. Ce travail de vérification repose aujourd'hui sur l'expertise des services juridiques, souvent sollicités dans l'urgence.

**Objectif**

MANUEL s'intègre directement dans Microsoft Word, l'outil de rédaction quotidien des collaborateurs parlementaires. En collant le projet de loi support et le texte de l'amendement, l'utilisateur obtient en moins d'une seconde :

- Un **verdict constitutionnel** : RECEVABLE, SUSPECT ou IRRECEVABLE
- Un **score de compatibilité thématique** entre l'amendement et le projet de loi
- Un **diagnostic par article** (45 / 40 / 41) avec niveau de risque
- Un **contrôle rédactionnel** automatique : structure, coordinations législatives, dispositions transitoires, formalisme procédural
- Une **explication juridique** rédigée, mobilisable en commission ou en séance

**Ce que MANUEL vérifie**

- *Article 45* : l'amendement est-il en lien suffisant avec le texte en discussion ? Détection des cavaliers législatifs par analyse des codes législatifs cités, classification thématique (~20 domaines du droit français) et similarité lexicale pondérée.
- *Article 40* : création de charge publique ou suppression de recettes sans gage de compensation ?
- *Article 41* : dispositions relevant du décret plutôt que de la loi (délais, modalités d'organisation, organigrammes) ?
- *Formalisme rédactionnel* : références aux subdivisions législatives correctes, formules de coordination, dispositions transitoires pour les suppressions d'institutions, entrée en vigueur, formules procédurales.

**Architecture technique**

MANUEL est une application web statique (HTML / CSS / JavaScript vanilla) déployée en add-in Word via un manifeste XML. Aucune donnée ne quitte le navigateur : l'analyse s'exécute entièrement côté client. L'extraction des textes depuis des PDF officiels est intégrée (PDF.js). Le moteur de scoring est modulaire : chaque article constitutionnel dispose de son propre module indépendant.

**Version actuelle**

Ce prototype a été développé en quelques jours dans le cadre du hackathon. Il couvre déjà les principaux motifs d'irrecevabilité, gère les PDF, s'intègre dans Word et produit des explications juridiques lisibles. C'est une base solide, pensée pour être étendue — voir le document de présentation joint pour la vision long terme.

### Image principale
![Image principale](images/cover.png)

### Contributeurs
- Lou-Anne Lombart
- Yacer
- Antoine

### Ressources utilisées

- [ ] `openfisca-france-parameters` — Base de données de paramètres ✺ OpenFisca
- [ ] `an-dossiers-legislatifs` — Dossiers législatifs de l'Assemblée nationale (législature courante) ✺ Assemblée nationale
- [x] `an-amendements-xvii` — Amendements déposés à l'Assemblée nationale (législature actuelle) ✺ Assemblée nationale
- [ ] `an-comptes-rendus` — Comptes rendus de la séance publique à l'Assemblée nationale (législature actuelle) ✺ Assemblée nationale
- [ ] `an-votes-xvii` — Votes des députés (législature actuelle) ✺ Assemblée nationale
- [ ] `an-deputes-en-exercice` — Députés en exercice ✺ Assemblée nationale
- [ ] `an-deputes-historique` — Historique des députés ✺ Assemblée nationale
- [ ] `an-deputes-senateurs-ministres-par-legislature` — Députés, sénateurs et ministres d'une législature ✺ Assemblée nationale
- [ ] `an-agenda-reunions` — Agenda des réunions à l'Assemblée nationale (législature courante) ✺ Assemblée nationale
- [ ] `an-questions-gouvernement` — Questions de l'Assemblée nationale au Gouvernement ✺ Assemblée nationale
- [ ] `an-questions-gouvernement-ecrites` — Questions écrites de l'Assemblée nationale au Gouvernement ✺ Assemblée nationale
- [ ] `an-questions-gouvernement-orales` — Questions orales de l'Assemblée nationale au Gouvernement ✺ Assemblée nationale
- [x] `premier-ministre-legi` — Codes, lois et règlements consolidés ✺ Premier ministre
- [ ] `premier-ministre-dole` — Dossiers législatifs Légifrance ✺ Premier ministre
- [ ] `premier-ministre-jorf` — Édition ''Lois et décrets'' du Journal officiel ✺ Premier ministre
- [ ] `senat-dispositifs-textes` — Dispositifs des textes déposés ou adoptés au Sénat ✺ Sénat
- [ ] `senat-dossiers-legislatifs` — Dossiers législatifs du Sénat ✺ Sénat
- [ ] `senat-amendements` — Amendements déposés au Sénat ✺ Sénat
- [ ] `senat-senateurs` — Sénateurs ✺ Sénat
- [ ] `senat-questions-gouvernement` — Questions orales et écrites du Sénat au Gouvernement ✺ Sénat
- [ ] `senat-comptes-rendus` — Comptes rendus de la séance publique au Sénat ✺ Sénat
- [ ] `an-et-co-database-regroupement-toutes-donnees` — Base de données unifiée Parlement / Législation / Service Public ✺ Assemblée nationale & communauté
- [ ] `an-et-co-serveur-mcp-regroupement-toutes-donnees` — Serveur MCP - Accès unifié Parlement / Législation / Service Public ✺ Assemblée nationale & communauté
- [ ] `an-et-co-api-regroupement-toutes-donnees` — API - Accès unifié Parlement / Législation / Service Public ✺ Assemblée nationale & communauté
- [ ] `legiwatch-api-parlement` — API Parlement ✺ LegiWatch
- [ ] `legiwatch-database-parlement` — Base de données Parlement ✺ LegiWatch
- [ ] `legiwatch-serveur-mcp-parlement` — Serveur MCP Parlement ✺ LegiWatch

### Galerie
- [Analyse d'un amendement CESER](images/image-1.png)
- [Diagnostic rédactionnel](images/image-2.png)

### Documents
- [Note de présentation — vision et potentiel](docs/note-presentation.pdf)

### URL de démonstration
https://buildwithasem.com/cavalier/

### Diapositives de présentation
[Diapositives de présentation](docs/diapositives.pdf)
