# Scénario 3 : Préparation d'un Jeu de Données Archéologiques pour Dépôt et Valorisation

Ce dossier illustre le troisième scénario de démonstration : l'accompagnement d'une archéologue fictive, Sophie Bernard, en fin de projet, qui souhaite préparer son jeu de données pour un dépôt dans un entrepôt de données FAIR comme NAKALA.

** Note ** : Cette démonstration tend à compliquer des processus qui peuvent être réalisés de manière beaucoup plus simples, elle est surtout à voir comme une démonstration technique plutôt qu'un réel workflow prêt à l'emploi.

## 1. Contexte de la Chercheuse

**Chercheuse (fictive) :** Sophie Bernard, archéologue.

**Phase du projet :** Fin de recherche. Sophie Bernard a collecté, traité et analysé un ensemble de données issues de fouilles archéologiques (inventaire d'artefacts, photographies, rapport de synthèse). Elle souhaite maintenant rendre ce jeu de données accessible, interopérable et réutilisable (principes FAIR) en le déposant dans un entrepôt de confiance.

**Besoin exprimé :**
* Obtenir des conseils pour structurer son jeu de données hétérogènes.
* Être aidée pour créer un fichier de métadonnées descriptives standardisé.
* Comprendre comment constituer un "paquet de dépôt" cohérent et bien documenté, en vue d'un dépôt sur NAKALA (Huma-Num).
* Choisir une licence de réutilisation appropriée.

## 2. Objectifs de l'Accompagnement (Démontrés dans ce Scénario)

L'objectif de cet accompagnement simulé, mis en œuvre via le Jupyter Notebook `preparation_depot_archeo.ipynb`, est de :
* Démontrer les bonnes pratiques pour organiser un jeu de données en vue de son archivage et de sa diffusion.
* Illustrer la création d'un fichier de métadonnées descriptives au format Dublin Core (XML) et JSON simple.
* Produire un "paquet de dépôt" exemplaire, incluant les données, les métadonnées, une documentation claire (`README_dataset.md`) et une licence (`LICENSE.txt`).
* Guider (théoriquement) la chercheuse dans les étapes d'un dépôt sur un entrepôt comme NAKALA.
* Mettre en avant l'importance des principes FAIR et de la documentation pour la valorisation des données de la recherche.

## 3. Description du Jeu de Données Archéologiques d'Exemple

Pour ce scénario, nous utilisons un jeu de données archéologiques **fictif** qui doit être **créé manuellement par l'utilisateur** et placé dans un dossier `source_data_archeo/` au même niveau que le notebook. Ce dossier doit contenir :

* **`inventaire_artefacts.csv` :** Un fichier CSV décrivant les artefacts.
    * Colonnes suggérées : `id_artefact`, `type_objet`, `materiau`, `periode_estimee`, `contexte_decouverte`, `description_courte`, `dim_L_cm`, `dim_l_cm`, `dim_h_cm_ou_epaisseur`, `poids_g`, `nom_fichier_photo`.
* **`images/` (sous-dossier) :** Contenant quelques fichiers images (ex: `artefact_001.jpg`, `VF_2023_CER_001.jpg`. Attention, ce sont des placeholders, les fichiers .jpg sont vides). Les noms de ces fichiers peuvent correspondre à ceux listés dans `inventaire_artefacts.csv`.
* **`rapport_synthese_VillaFloriana_2024.md` (ou `.txt`) :** Un fichier texte ou Markdown simulant un rapport de synthèse des fouilles.

## 4. Méthodologie Employée

Le notebook `preparation_depot_archeo.ipynb` met en œuvre les étapes suivantes :
1.  **Définition des paramètres :** Noms des dossiers source et de sortie.
2.  **Organisation des fichiers :** Création d'une structure de dossiers standardisée pour le paquet de dépôt (`data/`, `images/`, `documentation/`) et copie des fichiers sources d'exemple vers cette structure.
3.  **Génération des métadonnées :** Création d'un fichier `metadata_dublincore.xml` (et `metadata_simple.json`) à partir d'un dictionnaire Python contenant les informations descriptives du jeu de données (titre, auteur, description, mots-clés, licence, etc.), en respectant le schéma Dublin Core.
4.  **Création de la documentation :** Génération automatique d'un fichier `README_dataset.md` expliquant le contenu, la structure, la méthodologie et les conditions de réutilisation du jeu de données.
5.  **Choix et application d'une licence :** Création d'un fichier `LICENSE.txt` (basé sur Creative Commons CC BY 4.0).
6.  **(Optionnel) Archivage :** Création d'une archive `.zip` du paquet de dépôt complet.
7.  **Simulation du dépôt NAKALA :** Description textuelle des étapes typiques pour déposer le paquet sur un entrepôt comme NAKALA.

## 5. Structure du Dossier du Scénario

* **`preparation_depot_archeo.ipynb` :** Le Jupyter Notebook principal.
* **`README.md` (ce fichier) :** Présentation du scénario.
* **`source_data_archeo/` (à créer par l'utilisateur) :**
    * `inventaire_artefacts.csv`
    * `images/` (avec quelques fichiers `.jpg`)
    * `rapport_synthese_VillaFloriana_2024.md` (ou `.txt`)
* **`output_depot/` (généré par le notebook) :**
    * `depot_archeo_VillaFloriana_2024/` (le paquet de dépôt) :
        * `data/inventaire_artefacts.csv`
        * `images/` (contenant les images copiées)
        * `documentation/rapport_synthese_VillaFloriana_2024.md` (ou `.txt`)
        * `metadata_dublincore.xml` (généré)
        * `metadata_simple.json` (généré)
        * `README_dataset.md` (généré, placé à la racine du paquet)
        * `LICENSE.txt` (généré)
    * *(Optionnel)* `depot_archeo_VillaFloriana_2024.zip` (archive générée)

## 6. Comment Exécuter le Notebook

1.  **Prérequis :**
    * Avoir cloné l'ensemble du dépôt GitHub.
    * Disposer d'un environnement Python (>= 3.8 recommandé).
    * **Action Manuelle Indispensable :** Créez un dossier nommé `source_data_archeo/` au même niveau que le notebook `preparation_depot_archeo.ipynb`. Populez ce dossier avec les fichiers d'exemple décrits à la section 3 (un CSV, un sous-dossier `images/` avec quelques images, un rapport en `.md` ou `.txt`). *Le notebook ne fonctionnera pas sans ces fichiers sources.*
2.  **Installation des dépendances :**
    Naviguez à la racine du dépôt cloné et installez les bibliothèques requises :
    ```bash
    pip install -r requirements.txt
    ```
    (Ce scénario utilise principalement des modules Python standards comme `os`, `shutil`, `xml.etree.ElementTree`, `zipfile`, `datetime`, `json`, qui ne nécessitent généralement pas d'installation séparée si Python est déjà installé).
3.  **Lancement de Jupyter :**
    Ouvrez Jupyter Lab ou Jupyter Notebook :
    ```bash
    jupyter lab
    # ou
    # jupyter notebook
    ```
4.  **Ouverture et Exécution :**
    Naviguez jusqu'au dossier `scenario_3_valorisation_depot/` et ouvrez `preparation_depot_archeo.ipynb`. Exécutez les cellules séquentiellement. Le notebook créera le dossier `output_depot/` avec le paquet de dépôt structuré.

## 7. Description du Paquet de Dépôt Généré

Le notebook génère un dossier (par défaut `output_depot/depot_archeo_VillaFloriana_2024/`) qui constitue un exemple de "paquet de dépôt". Il contient :
* **Les données elles-mêmes :** organisées dans des sous-dossiers logiques (`data/`, `images/`, `documentation/`).
* **`metadata_dublincore.xml` :** Un fichier de métadonnées standardisé décrivant le jeu de données dans son ensemble. Ce fichier peut aider à remplir les formulaires de dépôt sur des entrepôts.
* **`metadata_simple.json` :** Une version JSON des métadonnées pour une autre forme d'utilisation.
* **`README_dataset.md` :** Un fichier de documentation crucial expliquant le contenu, le contexte, la méthodologie, la structure des fichiers et les conditions de réutilisation du jeu de données. Il est destiné aux futurs utilisateurs des données.
* **`LICENSE.txt` :** Un fichier texte spécifiant clairement la licence de réutilisation des données (CC BY 4.0 dans cet exemple).

Optionnellement, une archive ZIP de ce paquet est également créée pour faciliter son transfert.

## 8. Pistes pour la Suite (pour la chercheuse)

Après la préparation de ce paquet, la chercheuse pourrait :
* Affiner le contenu du `README_dataset.md` et des métadonnées pour qu'ils reflètent précisément son travail.
* Procéder au **dépôt effectif** du paquet sur NAKALA ou un autre entrepôt de données adapté à sa discipline et aux politiques de son institution.
* Une fois le jeu de données déposé et doté d'un identifiant pérenne (DOI), le **citer** dans ses publications.
* Envisager la rédaction d'un **"Data Paper"** : un article scientifique court décrivant le jeu de données pour en accroître la visibilité et la citabilité.

