
# Jeu de Données : Jeu de données archéologiques du site de la Villa Floriana (Bourgogne) - Campagne 2024

**Date de création du paquet :** 2025-05-21

## Auteur(s) et Contact

- **Créateur principal :** Bernard, Sophie (Dr.)
- **Contributeurs :** Équipe Archéologique Inrap Grand Est (fictif)
- **Institution de publication :** Université de Bourgogne (fictif) / Laboratoire ARTeHIS UMR 6298 (fictif)
- **Contact :** [email_chercheur@exemple.com] (à remplacer par un vrai contact)

## Description du Jeu de Données

Ce jeu de données comprend l'inventaire des artefacts (CSV), une sélection de photographies (JPG), et le rapport de synthèse (MD) issus des fouilles préventives menées en 2024 sur le site gallo-romain de la Villa Floriana en Bourgogne. Le site a livré des vestiges d'occupation s'étalant principalement du Ier au IVe siècle ap. J.-C.

**Mots-clés :** Archéologie, Gallo-Romain, Bourgogne, Villa Floriana, Artefacts, Céramique, Numismatique

**Couverture géographique :** Villa Floriana, Bourgogne, France (coordonnées fictives : 47.3220 N, 5.0415 E)
**Couverture temporelle des données :** Ier siècle ap. J.-C. - IVe siècle ap. J.-C.

## Méthodologie de Collecte/Production

Les données ont été collectées lors de fouilles archéologiques préventives sur le site de la Villa Floriana (Bourgogne) durant la campagne 2024. 
L'inventaire des artefacts a été réalisé selon les standards du [Nom de l'institution ou du projet]. 
Les photographies ont été prises en [Conditions de prise de vue].
Le rapport de synthèse fournit un aperçu des découvertes.
[Ajouter plus de détails sur la méthodologie spécifique si nécessaire]

## Structure du Jeu de Données et Formats des Fichiers

Le jeu de données est structuré comme suit :

- `data/inventaire_artefacts.csv` : Fichier CSV (séparateur virgule, encodage UTF-8) contenant l'inventaire détaillé des artefacts. 
  Colonnes : `id_artefact`, `type_objet`, `materiau`, `periode_estimee`, `contexte_decouverte`, `description_courte`, `dim_L_cm`, `dim_l_cm`, `dim_h_cm_ou_epaisseur`, `poids_g`, `nom_fichier_photo`.
- `images/` : Dossier contenant les photographies des artefacts sélectionnés (format JPEG).
- `documentation/rapport_synthese_VillaFloriana_2024.md` : Rapport de synthèse des fouilles (format Markdown).
- `metadata_dublincore.xml` : Fichier de métadonnées descriptives du jeu de données au format Dublin Core XML.
- `LICENSE.txt` : Fichier texte décrivant les conditions de réutilisation du jeu de données.
- `README_dataset.md` (ce fichier) : Informations générales sur le jeu de données.

## Conditions de Réutilisation et Citation

Ce jeu de données est diffusé sous la licence **Creative Commons Attribution 4.0 International (CC BY 4.0)**. 
Voir le fichier `LICENSE.txt` pour les détails complets de la licence. 
URL de la licence : https://creativecommons.org/licenses/by/4.0/

**Pour citer ce jeu de données :**
Bernard, Sophie (Dr.). (2025-05-21). *Jeu de données archéologiques du site de la Villa Floriana (Bourgogne) - Campagne 2024*. [Dataset]. Université de Bourgogne (fictif) / Laboratoire ARTeHIS UMR 6298 (fictif). 
Identifiant : [DOI qui sera assigné par NAKALA lors du dépôt, ex: 10.34847/xxxx]
[Adapter cette suggestion de citation aux normes de la discipline ou aux recommandations de l'entrepôt]

## Informations Complémentaires

[Ajouter ici toute information pertinente non couverte ailleurs, ex: logiciels spécifiques nécessaires pour ouvrir certains fichiers, projets de recherche liés, publications associées, etc.]
