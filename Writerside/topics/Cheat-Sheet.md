# Cheat Sheet

## 1. **Connexion à MongoDB**

- Démarrer MongoDB :
  ```bash
  mongod
  ```

- Se connecter à la base de données MongoDB :
  ```bash
  mongo
  ```

- Se connecter à une base spécifique :
  ```bash
  use nom_de_la_base
  ```

## 2. **Gestion des Bases de Données**

- Lister toutes les bases de données :
  ```bash
  show dbs
  ```

- Créer une base de données :
  ```bash
  use nom_de_la_base
  ```

- Supprimer une base de données :
  ```bash
  db.dropDatabase()
  ```

## 3. **Gestion des Collections (Tables)**

- Lister les collections dans la base de données :
  ```bash
  show collections
  ```

- Créer une collection :
  ```bash
  db.createCollection("nom_de_collection")
  ```

- Supprimer une collection :
  ```bash
  db.nom_de_collection.drop()
  ```

## 4. **Insertion de Données**

- Insérer un document (enregistre une entrée) :
  ```bash
  db.nom_de_collection.insertOne({ "champ1": "valeur1", "champ2": "valeur2" })
  ```

- Insérer plusieurs documents :
  ```bash
  db.nom_de_collection.insertMany([{ "champ1": "valeur1" }, { "champ2": "valeur2" }])
  ```

## 5. **Lecture des Données**

- Trouver tous les documents :
  ```bash
  db.nom_de_collection.find()
  ```

- Trouver un seul document :
  ```bash
  db.nom_de_collection.findOne({ "champ": "valeur" })
  ```

- Filtrer avec des conditions :
  ```bash
  db.nom_de_collection.find({ "champ": "valeur" })
  ```

- Limiter les résultats :
  ```bash
  db.nom_de_collection.find().limit(5)
  ```

## 6. **Mise à Jour des Données**

- Mettre à jour un document :
  ```bash
  db.nom_de_collection.updateOne({ "champ": "valeur" }, { $set: { "champ_a_mettre_a_jour": "nouvelle_valeur" } })
  ```

- Mettre à jour plusieurs documents :
  ```bash
  db.nom_de_collection.updateMany({ "champ": "valeur" }, { $set: { "champ_a_mettre_a_jour": "nouvelle_valeur" } })
  ```

## 7. **Suppression de Données**

- Supprimer un document :
  ```bash
  db.nom_de_collection.deleteOne({ "champ": "valeur" })
  ```

- Supprimer plusieurs documents :
  ```bash
  db.nom_de_collection.deleteMany({ "champ": "valeur" })
  ```

## 8. **Opérateurs de Recherche**

- `eq` (égalité) :
  ```bash
  db.nom_de_collection.find({ "champ": { $eq: "valeur" } })
  ```

- `gt` (plus grand que) :
  ```bash
  db.nom_de_collection.find({ "champ": { $gt: 10 } })
  ```

- `lt` (plus petit que) :
  ```bash
  db.nom_de_collection.find({ "champ": { $lt: 10 } })
  ```

- `in` (inclus dans un tableau) :
  ```bash
  db.nom_de_collection.find({ "champ": { $in: ["valeur1", "valeur2"] } })
  ```

- `exists` (existe) :
  ```bash
  db.nom_de_collection.find({ "champ": { $exists: true } })
  ```

## 9. **Indexation**

- Créer un index :
  ```bash
  db.nom_de_collection.createIndex({ "champ": 1 })  # 1 pour ordre croissant, -1 pour décroissant
  ```

- Lister les index :
  ```bash
  db.nom_de_collection.getIndexes()
  ```

- Supprimer un index :
  ```bash
  db.nom_de_collection.dropIndex("nom_de_l'index")
  ```

## 10. **Aggregation**

- Pipeline d'agrégation :
  ```bash
  db.nom_de_collection.aggregate([
    { $match: { "champ": "valeur" } },
    { $group: { _id: "$champ", total: { $sum: "$champ_a_sommer" } } }
  ])
  ```

## 11. **Backup et Restauration**

- Sauvegarder une base de données :
  ```bash
  mongodump --db nom_de_la_base --out /chemin/vers/sauvegarde
  ```

- Restaurer une base de données :
  ```bash
  mongorestore /chemin/vers/sauvegarde
  ```

## 12. **Utilisation de MongoDB avec Node.js**

- Installer MongoDB dans Node.js :
  ```bash
  npm install mongodb
  ```

- Exemple de connexion dans un fichier Node.js :
  ```javascript
  const { MongoClient } = require('mongodb');
  const uri = 'mongodb://localhost:27017';
  const client = new MongoClient(uri);

  async function run() {
    await client.connect();
    const database = client.db('nom_de_la_base');
    const collection = database.collection('nom_de_collection');
    const document = await collection.findOne({ "champ": "valeur" });
    console.log(document);
    await client.close();
  }

  run().catch(console.error);
  ```

