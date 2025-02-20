# Resume

## 1. NoSQL
### 📄 Définition {id="d-finition_1"}
NoSQL (Not Only SQL) est une famille de bases de données conçue pour gérer de grands volumes de données avec des modèles flexibles et une scalabilité élevée.

### 💪 Caractéristiques
- **🏢 Scalabilité horizontale** : Répartition des données sur plusieurs serveurs.
- **📝 Absence de schéma fixe** : Données stockées sous différents formats (JSON, BSON, colonnes, graphes, etc.).
- **⚡ Performances élevées** : Conçu pour des applications à fort volume de données.
- **🔬 Types de NoSQL** : Clé-Valeur, Colonnes, Documents, Graphes.

## 2. MongoDB
### 📚 Définition {id="d-finition_2"}
MongoDB est une base de données NoSQL orientée documents utilisant JSON comme format de stockage.

### 💎 Avantages
- **📃 Stockage sous forme de documents JSON** (BSON en interne).
- **📚 Schéma flexible** permettant des structures dynamiques.
- **🔍 Requêtes puissantes** avec JSON Query Language.
- **🎯 Scalabilité et performances élevées**.
- **🔒 Transactions ACID** pour assurer la cohérence des données.

### 📝 Opérations CRUD
- **➕ Create** : Ajout de documents.
- **📄 Read** : Lecture et recherche de données.
- **🗘️ Update** : Modification de documents.
- **❌ Delete** : Suppression de documents.

### 🛠️ Architecture
- **🛡️ Single Node** : Instance unique.
- **🔄 Replica Set** : Réplication pour haute disponibilité.
- **💪 Sharding** : Distribution des données pour scalabilité.

### 🔢 Indexation
- **🔍 Utilisation d'index** pour accélérer les recherches.
- **📝 Index simple et composé**.
- **🌐 Index textuel et géospatiaux**.

### 🔒 Sécurité
- **🔐 Authentification et autorisation** basées sur les rôles.
- **🔑 Chiffrement** des données en transit et au repos.
- **📊 Audit des actions**.

## 3. ELK (Elasticsearch, Logstash, Kibana)
### 📄 Définition
ELK est une suite d'outils open-source permettant la collecte, l'indexation, l'analyse et la visualisation de logs et données.

### 🔎 Elasticsearch
- **📑 Base de données orientée documents**.
- **🔍 Utilise Apache Lucene** pour un moteur de recherche rapide.
- **🛠️ API REST** pour les requêtes et interactions.
- **🔄 Sharding et réplication** pour une haute disponibilité.

### 📂 Logstash
- **🔄 Pipeline d'ingestion des données**.
- **🛠️ Prise en charge de sources multiples** (fichiers, bases de données, API).
- **🔧 Filtres et transformations** appliqués aux données.

### 📊 Kibana
- **🌍 Visualisation et analyse** des données.
- **📚 Tableaux de bord interactifs** avec graphiques et cartes.
- **🛠️ Exploration des logs** pour le débogage et la cybersécurité.

### 🤖 Beats
- **🛠️ Agents légers** pour collecter et envoyer les données à Logstash/Elasticsearch.
- Exemples : **📃 Filebeat** (fichiers logs), **📅 Metricbeat** (métriques système).

### 🔒 Sécurité {id="s-curit_1"}
- **🔑 Chiffrement** des communications entre nœuds.
- **🔐 Authentification et autorisation** via Kibana.
- **👥 Rôles et permissions** définis pour les utilisateurs.

### 📃 Exemple de Requête Elasticsearch
```sh
curl -X GET "localhost:9200/_search?q=user:john"
```

## 🏆 Conclusion
- **🔄 NoSQL** est idéal pour des données volumineuses et dynamiques.
- **📑 MongoDB** est un choix performant pour les applications orientées documents.
- **🔎 ELK** est une solution complète pour la gestion et l'analyse des logs.

Cette fiche de révision synthétise les concepts-clés pour t'aider à mieux comprendre et utiliser ces technologies. 📌🚀