# Scénario 1 : Exploration Initiale des Collections de Gallica pour l'Étude des Épidémies

Ce dossier contient les éléments relatifs au premier scénario de démonstration : l'accompagnement d'une historienne, Jeanne Dupont, dans la phase initiale de sa recherche sur la représentation des épidémies dans la presse française du XIXe siècle entre 1830 et 1870.

## 1. Contexte du Chercheur

**Chercheuse (fictive) :** Jeanne Dupont, historienne, spécialiste du XIXe siècle.

**Phase du projet :** Début de recherche. la chercheuse a une thématique précise mais a besoin d'un appui technique pour :
* Évaluer la richesse des collections numérisées de la BnF (Gallica) sur son sujet.
* Constituer un premier corpus de sources primaires (articles de presse).
* Comprendre comment accéder et exploiter ces documents numériquement.

## 2. Objectifs de l'Accompagnement (Démontrés dans ce Scénario)

L'objectif de cet accompagnement simulé, réalisé à travers le Jupyter Notebook `gallica_exploration_epidemies.ipynb`, est de :
* Identifier les titres de presse et estimer le volume de fascicules potentiellement pertinents dans Gallica traitant des épidémies durant la période 1830-1870.
* Extraire et structurer les métadonnées de base de ces documents (titre, périodique, date, identifiant ARK, lien Gallica).
* Fournir une première analyse exploratoire de ce corpus potentiel (répartition chronologique, principaux périodiques).
* Introduire les méthodes d'accès au contenu numérisé (images, OCR) via l'API IIIF de Gallica.
* Démontrer une démarche d'identification des problématiques, de conseil technique, et de proposition de solutions outillées.

## 3. Méthodologie Employée

L'approche adoptée dans le notebook est la suivante :

1.  **Définition des paramètres de recherche :**
    * **Mots-clés :** "choléra", "épidémie", "contagion", "typhus", "variole".
    * **Période :** 1830-1870.
    * **Type de document :** Fascicules de périodiques.
2.  **Interaction avec l'API SRU de Gallica :** Utilisation de requêtes HTTP (via la bibliothèque `requests` en Python) pour interroger l'endpoint SRU et récupérer les données en XML. La pagination est gérée pour collecter les résultats par lots.
3.  **Parsing XML et Extraction des Métadonnées :** Analyse des réponses XML (avec `xml.etree.ElementTree`) pour extraire les informations pertinentes (titre, date, identifiant ARK, source, etc.) selon le schéma Dublin Core.
4.  **Structuration des Données :** Utilisation de la bibliothèque `pandas` pour organiser les métadonnées extraites dans un DataFrame, facilitant le nettoyage (dédoublonnage par ARK), le traitement (extraction de l'année) et l'analyse.
5.  **Analyse Exploratoire Initiale :** Réalisation de comptages simples, identification des périodiques les plus fréquents, et visualisation de la distribution temporelle des documents (avec `matplotlib`).
6.  **Introduction à l'API IIIF :** Démonstration de la récupération d'un manifeste IIIF (JSON) pour un document exemple, et identification des pistes pour accéder aux images et aux fichiers OCR (ALTO XML).

## 4. Structure du Dossier

* **`gallica_exploration_epidemies.ipynb` :** Le Jupyter Notebook contenant tout le code Python, les explications de la démarche, et les visualisations des résultats.
* **`README.md` (ce fichier) :** Présentation du scénario, de la méthodologie et des résultats.
* **`output_data/` (généré par le notebook) :**
    * `gallica_epidemies_1830-1870_metadata_sample.csv` : Un échantillon des métadonnées structurées et nettoyées, au format CSV.
    * `sample_iiif_manifest_[ARK_ID].json` : Un exemple de manifeste IIIF téléchargé pour un document.
    * `plots/distribution_temporelle_1830-1870.png` : Un exemple de graphique généré montrant la distribution des documents par année.

## 5. Comment Exécuter le Notebook

1.  **Prérequis :** Assurez-vous d'avoir cloné l'ensemble du dépôt GitHub et d'avoir un environnement Python (>= 3.8 recommandé) configuré.
2.  **Installation des dépendances :** Naviguez à la racine du dépôt cloné et installez les bibliothèques nécessaires listées dans le fichier `requirements.txt` :
    ```bash
    pip install -r ../../requirements.txt
    # ou si vous êtes déjà à la racine du projet :
    # pip install -r requirements.txt
    ```
3.  **Lancement de Jupyter :** Ouvrez Jupyter Lab ou Jupyter Notebook depuis votre terminal :
    ```bash
    jupyter lab
    # ou
    # jupyter notebook
    ```
4.  **Ouverture du Notebook :** Naviguez jusqu'au dossier `scenario_1_exploration/` et ouvrez le fichier `gallica_exploration_epidemies.ipynb`.
5.  **Exécution des cellules :** Vous pouvez exécuter les cellules du notebook séquentiellement. Les requêtes API peuvent prendre quelques minutes en fonction de la charge des serveurs Gallica et du nombre de résultats.

## 6. Exemples de Résultats Clés et Limites


* **Volume de données :** Le notebook identifie 501 fascicules potentiellement pertinents sur la période 1830-1870 pour les mots-clés choisis (après dédoublonnage).
* **Distribution temporelle :** Une visualisation (graphique à barres, ex: `output_data/plots/distribution_temporelle_1830-1870.png`) montre la répartition de ces documents par année, mettant potentiellement en évidence des pics d'intérêt médiatique correspondant probablement à des vagues épidémiques connues (ex: choléra dans les années 1830 et 1860).
* **Périodiques clés ** : Recueil de médecine vétérinaire, le Figaro, Courrier des hôtels et Guide du commerce réunis : moniteur de l'exportation, etc
* **Accès au contenu :** Le notebook démontre comment obtenir l'URL d'un manifeste IIIF et identifier les chemins vers les images et les fichiers OCR (ALTO XML), quand ils sont disponibles.

**Limites de cette exploration initiale :**
* La recherche par mots-clés dépend de la qualité de l'OCR des documents numérisés par Gallica, qui peut varier.
* La pertinence réelle des documents doit être validée manuellement. Les mots-clés peuvent être polysémiques ou utilisés dans des contextes non pertinents.
* L'extraction du "titre de périodique" est une approche trop simple et pourrait être améliorée.
* Le nombre de résultats récupérés par mot-clé a été plafonné pour cette démonstration ; une recherche exhaustive pourrait ramener plus de documents.

## 7. Pistes pour la Suite (pour la chercheuse, Dr. Moreau)

Suite à cette première exploration, plusieurs pistes pourraient être envisagées :
* **Affiner la recherche :** Tester des variations de mots-clés, des expressions exactes, ou des recherches booléennes plus complexes.
* **Exploration ciblée :** Se concentrer sur les titres de presse identifiés comme les plus riches pour une analyse plus approfondie, numéro par numéro.
* **Récupération et traitement de l'OCR :** Pour une analyse de contenu (fouille de texte, analyse de sentiment, etc.), une étape ultérieure consisterait à télécharger et traiter les fichiers OCR (ALTO XML) des documents sélectionnés.
* **Analyse qualitative :** Lire et analyser un échantillon de documents pour évaluer leur pertinence et la nature des discours sur les épidémies.

