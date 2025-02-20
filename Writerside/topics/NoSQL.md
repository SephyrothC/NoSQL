# NoSQL
---

## **Transactions et Propriétés ACID**
### **Définition :** {id="d-finition_1"}
Une **transaction** est un ensemble d'opérations qui doivent être exécutées de manière fiable dans un système de base de données.

### **Propriétés ACID :**
1. **Atomicité** : Soit toutes les opérations sont exécutées, soit aucune n'est appliquée.
    - 📌 *Exemple : Un virement bancaire doit débiter un compte et créditer un autre. Si une des opérations échoue, tout doit être annulé.*
2. **Cohérence** : Après une transaction, la base doit rester dans un état valide.
    - 📌 *Exemple : Une commande e-commerce ne peut pas faire apparaître un produit en stock s'il a été vendu.*
3. **Isolation** : Les transactions concurrentes ne doivent pas interférer entre elles.
    - 📌 *Exemple : Deux clients ne peuvent pas réserver le dernier billet d'un vol en même temps.*
4. **Durabilité** : Une transaction validée est définitivement enregistrée.
    - 📌 *Exemple : Une confirmation de paiement ne doit pas disparaître après une panne du serveur.*

---

## **BASE : Alternative à ACID**
Contrairement à ACID, les systèmes **BASE** (Basically Available, Soft State, Eventual Consistency) offrent plus de flexibilité.

- **Basic Availability** : Il vaut mieux avoir une réponse incomplète que pas de réponse du tout.
- **Soft State** : L’état des données peut temporairement être incohérent.
- **Eventual Consistency** : Le système devient cohérent avec le temps.

📌 *Exemple : Un réseau social peut afficher des notifications avec un léger retard sans impacter l'expérience utilisateur.*

---

## **ACID vs BASE : Quel choix ?**
- **ACID** : Idéal pour les banques, e-commerce, bases de données relationnelles où la cohérence est critique.
- **BASE** : Adapté aux réseaux sociaux, moteurs de recherche, systèmes massivement distribués.

---

## **Théorème de Brewer (CAP)**
Un système distribué ne peut pas garantir simultanément ces trois propriétés :
1. **Cohérence** (*Consistency*) : Tous les nœuds ont les mêmes données au même moment.
2. **Disponibilité** (*Availability*) : Toutes les requêtes ont une réponse.
3. **Tolérance au partitionnement** (*Partition Tolerance*) : Le système fonctionne même en cas de coupure réseau.

💡 **Choix possible :**
- Cohérence + Disponibilité → Pas de tolérance aux partitions (*banques*).
- Cohérence + Tolérance aux partitions → Moins de disponibilité (*bases distribuées*).
- Disponibilité + Tolérance aux partitions → Moins de cohérence (*réseaux sociaux*).

---

## **Introduction au NoSQL**
Contrairement aux bases **SQL** (relationnelles), les bases **NoSQL** sont conçues pour gérer de grandes quantités de données distribuées, souvent non structurées.

📌 **Avantages de NoSQL :**  
✅ Stockage flexible 📂  
✅ Scalabilité horizontale 📈  
✅ Performance optimisée ⚡

---

## **Types de bases NoSQL**
1. **Clé / Valeur** 🗝️ → Rapide et simple (*Redis, DynamoDB*).
2. **Colonnes** 📊 → Données massives (*Cassandra, HBase*).
3. **Documents** 📜 → JSON-like, flexible (*MongoDB, CouchDB*).
4. **Graphes** 🔗 → Relations complexes (*Neo4j, ArangoDB*).

📌 *Exemple :*
- *MongoDB pour stocker des profils utilisateurs.*
- *Neo4j pour analyser les connexions entre personnes sur un réseau social.*

---

## **Big Data et ses Enjeux**
### **Définition :**
Le **Big Data** désigne le volume croissant de données numériques collectées en continu.

### **Les 4 V du Big Data**
1. **Volume** 📦 : Quantité énorme de données (Exabyte, Zettabyte…).
2. **Variété** 🌍 : Données structurées (bases SQL) et non structurées (textes, images, vidéos…).
3. **Vélocité** 🚀 : Flux de données en temps réel (*réseaux sociaux, IoT*).
4. **Véracité** 🎯 : Qualité et fiabilité des données (*fake news, erreurs*).

📌 *Exemple : Un moteur de recommandation comme Netflix analyse des millions d'interactions pour suggérer des films.*

---

## **Applications du Big Data**
- **Marketing** 🎯 → Personnalisation des publicités (*Amazon*).
- **Santé** 🏥 → Analyse des données médicales (*prévention, IA médicale*).
- **Finance** 💰 → Détection de fraudes (*cartes bancaires*).
- **Transport** 🚆 → Optimisation des trajets (*Google Maps, Uber*).

---

## **Big Data et Intelligence Artificielle**
Le Big Data alimente des algorithmes d’**IA** pour la prise de décision automatique :
✅ Analyse prédictive 📊
✅ Machine Learning 🤖
✅ Reconnaissance d’images 📸

---

## **Défis et Questions Éthiques**
💡 **Problèmes soulevés :**
- **Vie privée** 🔒 (*RGPD, données personnelles*).
- **Biais algorithmiques** ⚖️ (*discriminations*).
- **Sécurité des données** 🛡️ (*cyberattaques*).

📌 *Exemple : Facebook a été critiqué pour l’utilisation abusive des données personnelles dans des campagnes politiques.*

---

## **Conclusion**
Le NoSQL et le Big Data permettent d’exploiter d’énormes volumes de données en offrant plus de flexibilité que les bases relationnelles. Le choix entre **ACID et BASE**, ou **SQL et NoSQL**, dépend des besoins spécifiques d’un projet. 🚀

👉 **Question à se poser :** Quel est le meilleur compromis entre cohérence, performance et scalabilité pour mon application ? 🤔