# Segmentation Client – Customer Personality Analysis

Ce dépôt contient une étude de **segmentation client** réalisée à partir du jeu de données `Customer Personality Analysis` (`marketing_campaign.csv`).  
L’objectif est de regrouper les clients selon leurs **comportements d’achat** et leurs **caractéristiques démographiques** afin d’adapter la stratégie marketing.

---

## Notebooks disponibles

### 📘 `data_exploration.ipynb`

- Implémentation d’un **K-means « maison »** sur le jeu de données Iris.
- Analyse des résultats :
  - Méthode du coude.
  - Score de silhouette.
  - Comparaison avec l’implémentation Scikit-Learn.

### 📘 `customer_clustering.ipynb`

- **Préparation des données marketing** :
  - Nettoyage.
  - Traitement des dates.
  - Encodage des variables.
  - Suppression des outliers.
- Réduction de dimension via **PCA**.
- Application de plusieurs algorithmes de **clustering** :
  - K-means.
  - Clustering hiérarchique (CAH).
  - DBSCAN.
- Évaluation des clusters :
  - Variance expliquée.
  - Silhouette score.

---

## 🔍 Interprétation des segments

- **Cluster 0** – *Acheteurs réguliers promo-sensibles*  
  Clients réactifs aux promotions, revenus corrects, consommation modérée.

- **Cluster 1** – *Clients passifs à bas revenu*  
  Faible pouvoir d’achat, peu d’achats, répondent rarement aux campagnes.

- **Cluster 2** – *Premium engagés et gros consommateurs*  
  Très haut niveau de dépenses, forte réactivité aux offres marketing.

---

## 🔁 Reproduire l’analyse

1. Les données sources sont situées dans : `data/marketing_campaign.csv`.
2. Exécuter les notebooks dans cet ordre :
   - `data_exploration.ipynb` : implémentation du K-means personnalisé.
   - `customer_clustering.ipynb` : clustering sur les données marketing.

---

## 📦 Bibliothèques utilisées

- `pandas`
- `scikit-learn`
- `seaborn`
- `matplotlib`

---

## ✅ Conclusion

Cette étude met en évidence trois segments de clients aux profils marketing différenciés.  
Ces résultats permettent de **cibler plus efficacement les campagnes** et d’**optimiser les actions de fidélisation** selon le comportement et l’engagement des clients.

---

