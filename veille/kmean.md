# 🧠 K-means : Mathématiques et fonctionnement

## 🔍 Objectif

Diviser un ensemble de points (données) en **k groupes** (appelés *clusters*) de façon à ce que :
- les points d’un même groupe soient **proches les uns des autres** ;
- les groupes soient **aussi différents que possible** entre eux.

---

## ⚙️ Fonctionnement mathématique

### 1. Initialisation

On choisit **k centres de clusters** au hasard parmi les points (appelés *centroïdes*).

**Mathématiquement :**
On note ces centres comme des vecteurs :

```math
C_1, C_2, ..., C_k \in \mathbb{R}^n
```

---

### 2. Assignation des points aux centres

Pour chaque point, on calcule sa **distance au centre le plus proche**.

➡️ **Distance euclidienne** :

```math
d(x, C_i) = \sqrt{\sum_{j=1}^{n} (x_j - C_{i,j})^2}
```

Chaque point est assigné au cluster du centroïde le plus proche.

---

### 3. Mise à jour des centres

On recalcule le centre de chaque cluster comme la **moyenne de tous les points** qui lui sont assignés.

**Formule moyenne (barycentre)** :

```math
C_i = \frac{1}{n_i} \sum_{x \in cluster_i} x
```

---

### 4. Répétition

On **répète les étapes 2 et 3** jusqu’à ce que :
- les centres ne bougent presque plus (convergence),
- ou qu’un nombre maximal d’itérations soit atteint.

---

## 📉 Fonction à minimiser : l’inertie intra-cluster

K-means cherche à **minimiser la somme des distances au carré** entre chaque point et son centre.

```math
J = \sum_{i=1}^{k} \sum_{x \in cluster_i} ||x - C_i||^2
```

> Plus J est faible, plus les clusters sont compacts.

---

## 📌 Remarques importantes

- K-means **ne garantit pas** de trouver l’optimum global (à cause de l’initialisation aléatoire).