# ProjetWebSem

### 1. **Données utilisées**
Les données proviennent de la plateforme Open Food Facts, qui offre :
- Des fichiers au format CSV.
- Un fichier RDF contenant des données sémantiques.

Nous avons travaillé principalement avec :
- Le fichier CSV contenant les données des produits alimentaires.
- Le fichier `data-fields.txt` pour identifier les concepts et leurs propriétés.
  
### 2. **Préparation des données**
- **Partitionnement :** Le fichier CSV volumineux a été scindé en fichiers de 10 000 lignes pour une meilleure manipulation.
  
- **Extraction :** Sélection des colonnes pertinentes pour nos variables d'intérêt (produit, marque, ingrédients, valeurs nutritionnelles, etc.).


### 3. **Conception de l'ontologie**

#### Outils utilisés :
- **Protégé** : Création et gestion des classes, propriétés et relations.
- **Python** : Automatisation de la génération de triplets RDF à partir des données CSV.
#### Étapes principales :
- Définition des concepts principaux :
  - Produit alimentaire, catégorie, marque, ingrédient, valeur nutritionnelle, allergène, etc.
- Création des relations entre concepts :
  - Exemple : `Produit` **a pour marque** `hasBrand` → `Marque`.
- Utilisation de vocabulaires comme FOAF et Schema.org pour garantir l'interopérabilité.

### 4. **Peuplement du graphe de connaissances**
- Transformation des données structurées en triplets RDF.
- Exportation des données RDF au format Turtle et JSON-LD.

### 5. **Stockage et interrogation**
- Utilisation de **GraphDB** comme triplestore pour :
  - Stocker les données RDF.
  - Exécuter des requêtes SPARQL simples et complexes.

#### Exemples de requêtes SPARQL :
- **Requêtes simples :**
  - Trouver les informations détaillées sur un produit spécifique.
  - Identifier les catégories et marques associées à un produit.
- **Requêtes complexes :**
  - Génération de sous-graphes RDF en fonction de filtres (quantité > 10, catégorie spécifique).
### 6. **Enrichissement des données**

#### Sources utilisées :
- **DBpedia** et **Wikidata** pour :
  - Associer les marques, catégories et pays à des entités existantes (QCodes).
  - Relier les données locales à des ressources du web sémantique.

### 7. **Interrogation des données enrichies**
- Exécution de requêtes fédérées pour récupérer des informations complémentaires sur les produits.
- Exemple : Trouver le QCode de chaque catégorie ou associer une marque à ses produits, pays et catégories.
  
## Technologies utilisées
- **Protégé** : Conception de l'ontologie.
- **Python** :
  - Bibliothèques : `rdflib`, `SPARQLWrapper`.
  - Automatisation des tâches de transformation de données.
- **GraphDB** : Stockage des triplets RDF et exécution des requêtes SPARQL.
- **DBpedia/Wikidata** : Enrichissement et interopérabilité.

### Notes importantes
- Les données RDF générées doivent être conformes aux standards de FOAF et Schema.org.
- L'enrichissement avec DBpedia et Wikidata nécessite une connexion internet.

## Membres de l'équipe
- **Salimata Cissouma**
- **Mohammedi Amira** *(amira.mohammedi@etu.univ-grenoble-alpes.fr)*
- **Gaelle Manuela Yonga Yonga** *(gaelle.yonga-yonga@etu-univ)*

## Superviseur
- **Danielle**
