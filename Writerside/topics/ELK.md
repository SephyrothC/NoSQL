# ELK

## **1. Introduction à ELK**
La stack **ELK** est un ensemble d'outils open-source permettant la collecte, le stockage, l'analyse et la visualisation des logs. Elle est composée de :
- 📦 **Elasticsearch** : moteur de recherche et base de données NoSQL.
- 🔄 **Logstash** : outil de collecte et transformation des données.
- 📊 **Kibana** : interface de visualisation des données.
- 🎧 **Beats** (optionnel) : agents légers pour la collecte des logs.

## **2. NoSQL et ELK**
### **Définitions simplifiées** 
- 📂 **NoSQL** : Type de base de données qui ne suit pas le modèle relationnel classique. Idéal pour les données volumineuses et non structurées.
- 🌍 **Architecture distribuée** : Système où les données et les traitements sont répartis sur plusieurs serveurs.
- 🔄 **Réplication** : Copie des données sur plusieurs serveurs pour assurer la disponibilité.
- ⚡ **Parallélisation** : Traitement simultané de plusieurs tâches pour améliorer les performances.

## **3. Elasticsearch** 
### **Caractéristiques**
- 📄 Base de données orientée **documents JSON**.
- 🔍 Moteur de recherche basé sur **Apache Lucene**.
- 🌐 Interface **API REST** pour les requêtes et la gestion des données.
- ⚡ Conçu pour **analyser et rechercher de gros volumes de données rapidement**.

### **Exemple d'utilisation**
Un site e-commerce peut utiliser **Elasticsearch** pour permettre aux utilisateurs de rechercher des produits par nom, catégorie ou prix. 🛍️🔍💰

## **4. Logstash** 
### **Rôle et fonctionnement**
- 📥 **Collecte** de données depuis différentes sources (fichiers logs, bases de données, API, etc.).
- 🔄 **Filtrage et transformation** des données (ex. suppression de champs inutiles, enrichissement des logs).
- 📤 **Envoi** des données vers **Elasticsearch** ou d'autres destinations.

### **Exemple** {id="exemple_1"}
Un serveur Web génère des logs d'accès. **Logstash** peut récupérer ces logs, extraire les informations utiles (IP, URL demandée, temps de réponse) et les envoyer vers **Elasticsearch**. 🌐📜📈

## **5. Kibana** 
### **Fonctionnalités principales**
- 📊 Création de **dashboards interactifs**.
- 📈 Visualisation sous forme de **graphiques, cartes et diagrammes**.
- 🔎 Outils pour explorer et analyser les données indexées dans **Elasticsearch**.

### **Exemple**
Un administrateur réseau peut utiliser **Kibana** pour afficher un tableau de bord avec le **nombre de requêtes HTTP reçues par minute** et identifier des anomalies. 🌍📡🔎

## **6. Beats** 
- 🗂️ Agents légers qui collectent des logs et les envoient vers **Logstash** ou **Elasticsearch**.
- 📄 Exemples :
    - 📜 **Filebeat** : collecte des fichiers logs.
    - 📊 **Metricbeat** : collecte des métriques système.
    - 🌐 **Packetbeat** : surveille le trafic réseau.

## **7. Vocabulaire important** 
- 🖥️ **Node** : Instance Elasticsearch en fonctionnement.
- 🔗 **Cluster** : Ensemble de plusieurs nodes travaillant ensemble.
- 📄 **Document** : Unité d'information de base (stockée en JSON).
- 📂 **Index** : Collection de documents similaires (équivalent à une table SQL).
- 🧩 **Shard** : Fragment d'un index pour améliorer la répartition et la performance.

## **8. Transactions et cohérence** 
- ❌ **Pas de rollback** : Impossible d'annuler une opération après exécution.
- 📜 **Log de transactions (Write Ahead Log)** pour garantir la durabilité des écritures.
- ⚡ **Conçu pour la rapidité**, pas pour la gestion stricte des transactions comme une base SQL.

## **9. Schéma flexible** 
- 📜 **Pas de schéma fixe** : Elasticsearch devine les types de données.
- 📊 **Les analyses avancées nécessitent des schémas définis** pour de meilleures performances.

## **10. Relations et contraintes** 
- 📂 **Base orientée documents** : Tous les documents sont indexés pour des requêtes rapides.
- ⚠️ **Difficulté à maintenir la cohérence** des données.
- 🚀 **Idéal pour les charges de type Write-Once-Read-Many** (beaucoup d'écritures, peu de mises à jour).

## **11. Distribution et scalabilité** 
- 🌎 Conçu pour être **distribué** (les données sont réparties sur plusieurs machines).
- 🏛️ Utilise un **système de quorum** pour garantir la cohérence des données.
- 🧩 Division des index en **shards** pour améliorer les performances et la disponibilité.

## **12. Sécurité dans ELK** 
- 🔐 **Elasticsearch** : Chiffrement des communications entre nodes.
- 🔑 **Kibana** : Authentification (interne/externe) et gestion des rôles.

## **13. Installation et premier test** 
- 📦 **Elasticsearch** : Nécessaire pour les autres composants.
- 📊 **Kibana** : Interface graphique pour Elasticsearch.
- 🔄 **Logstash** : Récupère et traite les logs.

### **Premier test avec Elasticsearch**
Commande pour vérifier qu'Elasticsearch fonctionne :
```sh
curl http://localhost:9200
```
Réponse typique :
```json
{
 "name" : "elk1",
 "cluster_name" : "elasticsearch",
 "version" : {
 "number" : "7.16.2",
 "lucene_version" : "8.10.1"
 },
 "tagline" : "You Know, for Search"
}
```

## **14. Interactions avec Elasticsearch**
- 🛠️ **CRUD** :
    - 📝 **Create** : Ajouter un document.
    - 📖 **Read** : Lire un document.
    - ✏️ **Update** : Modifier un document.
    - ❌ **Delete** : Supprimer un document.
- 🌐 **API REST et interface Kibana** pour interagir avec les données.

---

### **Conclusion** 🎯📊💡
La stack **ELK** est un outil puissant pour **la gestion et l'analyse des logs**. Grâce à son **architecture distribuée**, son **moteur de recherche performant**, et ses **capacités de visualisation avancées**, elle est largement utilisée pour la **cybersécurité, la supervision de serveurs et l'analyse de données en temps réel**.

💡 **Exemple concret** : Une entreprise utilise **ELK** pour surveiller ses serveurs en temps réel et détecter des tentatives d'intrusion en analysant les logs d'accès. 🛡️📉🚨

---

