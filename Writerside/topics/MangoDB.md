# MangoDB

## **Introduction à MongoDB**
MongoDB est une **base de données NoSQL** qui stocke les données sous forme de **documents JSON**. Contrairement aux bases relationnelles (SQL), elle permet une grande flexibilité et une scalabilité horizontale.

### **Pourquoi MongoDB ?**
- **Moderne** : Conçu pour les applications web et big data.
- **Populaire** : Utilisé par de nombreuses entreprises.
- **Stockage en Documents** : Données sous format JSON.
- **Langage de requête JSON** : Manipulation des données facile.
- **Écosystème riche** : Connecteurs pour plusieurs langages (Python, Node.js, etc.).

---
## **Concepts de base**

### **Base de données document (Document Database)**
- **Documents JSON** : Stockage des données en objets similaires à JSON.
- **Tableaux et objets imbriqués** : Permet une structure riche et flexible.
- **Schéma flexible** : Pas besoin de définir un schéma strict comme en SQL.
- **Opérations ACID** : MongoDB supporte les transactions pour assurer la cohérence des données.
- **Requêtes avancées** : Recherche textuelle, géospatiale et agrégation.
- **Jointures** : Possibles via `$lookup`.

📌 *Exemple : Stockage d’un utilisateur*
```json
{
  "nom": "Dupont",
  "email": "dupont@email.com",
  "âge": 30,
  "adresse": {
    "rue": "10 rue des Lilas",
    "ville": "Paris"
  }
}
```

---
## **Opérations CRUD** (Create, Read, Update, Delete)
MongoDB permet de manipuler les données facilement :
- **Create** : Ajouter des documents.
- **Read** : Lire des documents.
- **Update** : Modifier des documents existants.
- **Delete** : Supprimer des documents.

📌 *Exemple : Ajouter un utilisateur*
```json
{
  "nom": "Martin",
  "email": "martin@email.com",
  "âge": 25
}
```
Commande MongoDB :
```javascript
db.utilisateurs.insertOne({ nom: "Martin", email: "martin@email.com", âge: 25 })
```

---
## **Agrégation (Aggregation Pipeline)**
MongoDB permet d'effectuer des traitements avancés sur les données via le **pipeline d’agrégation**.

📌 *Exemple : Calculer l’âge moyen des utilisateurs*
```javascript
db.utilisateurs.aggregate([
  { $group: { _id: null, ageMoyen: { $avg: "$âge" } } }
])
```

---
## **Modélisation des données**

### **Modèle dénormalisé**
- Toutes les données liées sont stockées dans un seul document.
- Améliore les performances de lecture.

📌 *Exemple : Stocker les commandes d’un utilisateur directement dans le document utilisateur.*

### **Modèle normalisé**
- Utilisation de références pour lier les données.
- Meilleure gestion de la redondance des données.

📌 *Exemple : Stocker les ID des commandes dans le document utilisateur et les détails dans une autre collection.*

---
## **Architecture et Scalabilité**
### **Types d’architectures**
- **Single node** : Instance unique de MongoDB.
- **Replica Set** : Plusieurs copies des données pour assurer la disponibilité.
- **Sharding** : Répartition des données sur plusieurs serveurs pour améliorer la scalabilité.

### **Replica Set** (Répartition des données sur plusieurs serveurs)
- **Redondance** : Plusieurs copies des données.
- **Tolérance aux pannes** : Si un serveur tombe en panne, un autre prend le relais.
- **Asynchronous replication** : Les données sont synchronisées en différé.

📌 *Exemple : Une entreprise utilise un Replica Set pour assurer la disponibilité de sa base de données même en cas de panne d’un serveur.*

### **Sharding (Répartition des données sur plusieurs machines)**
- **Scalabilité horizontale** : Ajout de serveurs pour gérer plus de données.
- **Équilibrage automatique** : Répartition intelligente des données.
- **Shard keys** : Clés utilisées pour diviser les données.

📌 *Exemple : Un site e-commerce utilise le sharding pour répartir les commandes clients sur plusieurs serveurs.*

---
## **Indexation et Performances**
- **Index** : Structures optimisant la recherche de données.
- **Éviter les scans complets** : Recherche plus rapide.

📌 *Exemple : Créer un index sur le champ `email`*
```javascript
db.utilisateurs.createIndex({ email: 1 })
```

---
## **Transactions et Cohérence**
- **Atomicité** : Toutes les opérations réussissent ou échouent ensemble.
- **Lecture cohérente** : Choix du niveau de cohérence (`majority`, `local`, `snapshot`).
- **Une transaction par session** : Toutes les modifications doivent être incluses dans la même transaction.

📌 *Exemple : Effectuer un virement bancaire entre deux comptes*
```javascript
const session = db.getMongo().startSession();
session.startTransaction();
db.comptes.updateOne({ id: 1 }, { $inc: { solde: -100 } });
db.comptes.updateOne({ id: 2 }, { $inc: { solde: 100 } });
session.commitTransaction();
```

---
## **Sécurité**
- **Contrôle d’accès basé sur les rôles (RBAC)** : Gestion des permissions.
- **Authentification** : Connexion sécurisée (mot de passe, LDAP, Kerberos, x509).
- **Chiffrement** : TLS/SSL pour les données en transit, chiffrement au repos.
- **Audit** : Journalisation des accès et des modifications.

📌 *Exemple : Restreindre l’accès à une base de données à un utilisateur spécifique.*
```javascript
db.createUser({
  user: "admin",
  pwd: "password123",
  roles: [{ role: "readWrite", db: "maBase" }]
});
```

---
## **Conclusion**
MongoDB est une **solution NoSQL puissante**, adaptée aux applications modernes nécessitant **scalabilité, flexibilité et performance**. Grâce à son **modèle orienté documents**, sa **gestion des transactions ACID**, son **réplica set** et son **sharding**, il permet d’optimiser la gestion de grandes quantités de données de manière efficace.

💡 **À retenir** :
- ✅ Stockage en documents JSON.
- ✅ Scalabilité horizontale avec sharding.
- ✅ Haute disponibilité avec Replica Set.
- ✅ Sécurité renforcée et transactions ACID.
- ✅ Requêtes puissantes et indexation avancée.

MongoDB est idéal pour les applications web, les big data et les systèmes distribués nécessitant de la flexibilité et des performances accrues. 🚀


## **Cheatsheet MongoDB**
[Cliquez ici pour accéder à la fiche de révision MongoDB](Cheat-Sheet.md)