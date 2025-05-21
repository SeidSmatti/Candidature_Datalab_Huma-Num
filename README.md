# Projet de Démonstration : Appui au Traitement des Données Scientifiques

Ce dépôt GitHub a pour objectif de présenter de manière concrète mes compétences et ma compréhension de certaines des missions pour le poste de **Chargé d'appui au traitement des données scientifiques au BnF DataLab et à l'IR* Huma-Num CNRS (Référence : UAR3598-ARIALL-040)**.

Il simule l'accompagnement de trois chercheurs fictifs, chacun se trouvant à une étape différente de son projet de recherche et confronté à des problématiques spécifiques de traitement de données scientifiques en sciences humaines et sociales. Chaque scénario est implémenté sous forme de Jupyter Notebooks documentés.

## Aperçu des Scénarios

Le projet s'articule autour de trois scénarios distincts qui se placent à différentes temporalités de la vie d'un projet :

1.  **Scénario 1 : L'Historienne en début de recherche – "Identifier des sources pour une étude sur la représentation des épidémies dans la presse française du XIXe siècle via Gallica"**
    * **Chercheur(se) :** Jeanne Dupont (fictive), historienne.
    * **Problématique :** En début de recherche, la chercheuse a besoin d'aide pour constituer un corpus initial à partir des collections numérisées de la BnF (Gallica) sur le thème des épidémies.
    * **Objectif de l'accompagnement simulé :** Aider à l'identification des sources pertinentes via l'API SRU de Gallica, à l'extraction des métadonnées (XML), à la structuration de ces données (Pandas), et à une première analyse exploratoire (volume, répartition temporelle).
    * ** Lien vers le scénario :** [`./chercheur_1_exploration/`](./chercheur_1_exploration/)

2.  **Scénario 2 : Le sociolinguiste en pleine analyse – "Traiter et analyser un corpus de témoignages oraux transcrits pour étudier les variations linguistiques"**
    * **Chercheur(se) :** Jean Dupont (fictif), sociolinguiste.
    * **Problématique :** Le chercheur dispose de transcriptions textuelles d'entretiens oraux et souhaite les nettoyer, les structurer, et appliquer des techniques de Traitement Automatique de la Langue (TAL) pour en extraire des informations pertinentes.
    * **Objectif de l'accompagnement simulé :** Proposer un pipeline de traitement incluant la lecture des fichiers, la segmentation par locuteur, le nettoyage des annotations d'oralité, l'enrichissement TAL avec `spaCy` (lemmatisation, étiquetage morpho-syntaxique, reconnaissance d'entités nommées), et des analyses quantitatives initiales (fréquences lexicales, TTR, nuages de mots, distribution des catégories grammaticales).
    * ** Lien vers le scénario :** [`./chercheur_2_traitement_analyse/`](./chercheur_2_traitement_analyse/)

3.  **Scénario 3 : L'archéologue prête à partager – "Préparation et dépôt d'un jeu de données de fouilles pour NAKALA"**
    * **Chercheur(se) :** Dr. Sophie Bernard (fictive), archéologue.
    * **Problématique :** En fin de projet, Dr. Bernard souhaite déposer son jeu de données hétérogènes (données tabulaires CSV, images, rapport textuel) de manière FAIR dans un entrepôt de confiance.
    * **Objectif de l'accompagnement simulé :** Conseiller sur la structuration du jeu de données selon les principes FAIR, la création de métadonnées descriptives standardisées (Dublin Core, générées en XML et JSON), la constitution d'un "paquet de dépôt" complet (données, métadonnées, `README_dataset.md`, `LICENSE.txt`), et simuler la démarche pour un dépôt sur un entrepôt type NAKALA (Huma-Num).
    * ** Lien vers le scénario :** [`./chercheur_3_valorisation_depot/`](./chercheur_3_valorisation_depot/)

## Structure du Dépôt

Chaque scénario est contenu dans son propre dossier (ex: `chercheur_1_exploration/`) et comprend :
* Un `README.md` spécifique détaillant le contexte, la méthodologie, et les résultats du scénario.
* Un Jupyter Notebook (`.ipynb`) implémentant le workflow de traitement et d'analyse.
* Des données d'exemple (`corpus_exemple/` ou `source_data_archeo/`) nécessaires pour exécuter le notebook.
* Des résultats générés (`output_data/`) par l'exécution du notebook (fichiers CSV, graphiques, paquet de dépôt, etc.).

## Compétences Démontrées

Ce projet vise à illustrer les compétences suivantes, en adéquation avec l'offre d'emploi :

**Savoirs :**
* **Connaissance des enjeux numériques des institutions patrimoniales :** Démontrée par l'interaction avec les collections de la BnF (Gallica via API SRU/IIIF dans le Scénario 1), la préparation d'un jeu de données pour dépôt dans un entrepôt de type Huma-Num (NAKALA, Scénario 3), et la discussion des principes FAIR pour la valorisation des données.
* **Connaissance d’un langage de programmation (Python) et de son utilisation dans le cadre de traitement de données :** Utilisé de manière centrale dans les trois scénarios pour la collecte de données (S1), le nettoyage et l'analyse textuelle (S2), la génération de métadonnées, la manipulation de fichiers et la création de paquets de dépôt (S3).
* **Connaissance des logiciels professionnels couramment utilisés (éditeur XML, logiciels de mise en forme de données, dépôts de code git, Jupyter notebooks…) :** Ce projet est géré avec Git et hébergé sur GitHub. Les Jupyter Notebooks servent d'environnement de travail, de démonstration et de documentation interactive. Des scripts Python sont utilisés pour la mise en forme et la génération de fichiers (XML dans S3).
* **Connaissance des outils d'exploration (data mining) et d'extraction des données (data extraction / web scraping) :** Le Scénario 1 illustre l'extraction de métadonnées via l'API SRU de Gallica. Le Scénario 2 met en œuvre des techniques de fouille de texte de base (calcul de fréquences, TTR, identification d'entités nommées).
* **Connaissance du fonctionnement des API (REST, GraphQL) et des formats d'échange de données (JSON, XML) :** Le Scénario 1 interagit avec l'API SRU (XML) et IIIF (JSON) de Gallica. Le Scénario 3 génère des métadonnées en XML (Dublin Core) et en JSON.
* **Connaissance des usages et technologies du web sémantique : normes et standards d'interopérabilité, métadonnées, datamining :** Mise en application des standards de métadonnées (Dublin Core dans Scénario 3), discussion sur l'intérêt de TEI pour les corpus oraux (Scénario 2), et utilisation d'API standardisées pour l'accès aux données patrimoniales (Scénario 1).
* **Capacité d'apprentissage et d'appropriation des nouvelles technologies :** Mise en œuvre et adaptation de diverses bibliothèques Python (telles que `requests`, `pandas`, `spacy`, `xml.etree.ElementTree`, `wordcloud`, `matplotlib`) pour répondre aux problématiques spécifiques de chaque scénario.
* **Maîtrise des techniques de présentation orale et écrite, de rédaction de documents de synthèse :** Illustrée par la structure de ce `README.md` principal, des `README.md` spécifiques à chaque scénario, ainsi que par les explications et commentaires fournis au sein des Jupyter Notebooks.

**Savoir-être (illustrés par la démarche et la qualité du projet) :**
* **Savoir travailler en équipe :** Approche collaborative simulée à travers l'accompagnement des chercheurs fictifs, en se concentrant sur leurs besoins.
* **Avoir le sens de l'organisation, autonomie :** Manifesté par la structure claire et logique du dépôt, la modularité des scénarios, et la reproductibilité des workflows.
* **Être force de proposition :** Démontré par la conception de scénarios pertinents et la proposition de solutions techniques et méthodologiques adaptées à chaque cas.
* **Faire preuve de rigueur et de fiabilité :** Objectif visé à travers un code fonctionnel, une documentation précise, et des résultats cohérents et interprétables.
* **Savoir rendre compte :** Illustré par la qualité de la documentation, la clarté des explications des démarches entreprises et des résultats obtenus.

## Mise en Route

Pour explorer ce projet et exécuter les notebooks :

1.  **Clonez le dépôt :**
    ```bash
    git clone https://github.com/SeidSmatti/Candidature_Datalab_Huma-Num
    cd Candidature_Datalab_Huma-Num
    ```

2.  **Créez un environnement virtuel et installez les dépendances :**
    Il est fortement recommandé d'utiliser un environnement virtuel Python (ex: venv, conda).
    ```bash
    python -m venv .venv
    source .venv/bin/activate  # Sur Windows : .venv\Scripts\activate
    pip install -r requirements.txt
    ```
    Le fichier `requirements.txt` à la racine du projet liste toutes les bibliothèques Python nécessaires. N'oubliez pas de télécharger les modèles de langue spaCy si nécessaire (voir README des scénarios concernés), aussi spaCy est à ce jour (21 mai 2025) incompatible avec Python 3.13, merci d'exécuter ce notebook dans une version antérieure.

3.  **Lancez JupyterLab ou Jupyter Notebook :**
    ```bash
    jupyter lab
    # ou
    # jupyter notebook
    ```
    Naviguez ensuite vers les dossiers des scénarios (`chercheur_1_exploration/`, `chercheur_2_traitement_analyse/`, `chercheur_3_valorisation_depot/`) pour ouvrir les notebooks `.ipynb` respectifs.

4.  **Explorez les scénarios :**
    Chaque dossier de scénario contient un `README.md` spécifique avec des instructions et des explications détaillées pour exécuter le notebook correspondant.

## Technologies Utilisées

* **Langage principal :** Python 3.x
* **Environnement :** Jupyter Notebooks / JupyterLab
* **Bibliothèques Python clés :**
    * `requests` (pour les requêtes API HTTP - Scénario 1)
    * `xml.etree.ElementTree` (pour le parsing et la génération XML - Scénarios 1 & 3)
    * `pandas` (pour la manipulation de données tabulaires - Scénarios 1, 2, 3)
    * `matplotlib` / `seaborn` (pour les visualisations graphiques - Scénarios 1 & 2)
    * `spacy` (pour le Traitement Automatique de la Langue - Scénario 2)
    * `wordcloud` (pour la génération de nuages de mots - Scénario 2)
    * `os`, `shutil`, `re`, `json`, `zipfile`, `datetime` (modules standards Python)
* **Gestion de version :** Git & GitHub
* **Formats de données manipulés :** XML, JSON, CSV, TXT, Markdown.

## Licence

Ce projet est distribué sous la licence publique générale GNU version 3 (GPLv3). Voir le fichier LICENSE.md pour plus de détails.

---

## English Summary 

*This GitHub repository serves as a practical demonstration of skills and understanding for the "Scientific Data Processing Support Officer" role at BnF DataLab and IR* Huma-Num CNRS (Reference: UAR3598-ARIALL-040).*

*It simulates providing support to three fictional researchers at different stages of their projects, addressing various challenges in scientific data processing within the humanities and social sciences. The project is divided into three scenarios, each implemented as a documented Jupyter Notebook:*

1.  ***Scenario 1: Early-Stage Historian*** *- Focuses on initial corpus building from BnF's Gallica digital library using its SRU API, metadata extraction (XML), data structuring with Pandas, and basic exploratory analysis.*
2.  ***Scenario 2: Mid-Research Sociolinguist*** *- Demonstrates a pipeline for processing a corpus of transcribed oral interviews, including text cleaning, speaker segmentation, NLP enrichment with spaCy (lemmatization, POS tagging, NER), and initial quantitative linguistic analysis (frequencies, TTR, word clouds).*
3.  ***Scenario 3: Archaeologist Ready to Share*** *- Guides through the preparation of a heterogeneous archaeological dataset (CSV, images, report) for FAIR deposit in a trusted repository like Huma-Num's NAKALA. This includes data structuring, Dublin Core metadata generation (XML & JSON), creating comprehensive documentation (`README_dataset.md`), choosing a license, and packaging the data.*

*Each scenario's folder contains a specific README, the Jupyter Notebook, example source data, and outputs generated by the notebook. The project primarily uses Python with common data science and digital humanities libraries.*
