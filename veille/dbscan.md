# 🧠 DBSCAN : Mathématiques et fonctionnement

## 🔍 Objectif

DBSCAN (Density-Based Spatial Clustering of Applications with Noise) identifie des **clusters de densité élevée** et isole les points éloignés comme du **bruit**.

> Contrairement à K-means, DBSCAN **ne nécessite pas de spécifier le nombre de clusters**.

---

## ⚙️ Paramètres clés

- **ε (epsilon)** : rayon de voisinage
- **MinPts** : nombre minimal de points requis dans un voisinage pour être considéré comme un noyau de cluster

---

## 🧩 Types de points

| Type de point     | Définition |
|-------------------|------------|
| **Point noyau**   | ≥ MinPts dans son voisinage ε |
| **Point bordure** | < MinPts dans ε, mais voisin d’un point noyau |
| **Bruit**         | Ni noyau, ni bordure |

---

## 📐 Distance et voisinage

On utilise souvent la **distance euclidienne** pour mesurer le voisinage :

```math
d(x, y) = \sqrt{\sum_{i=1}^{n} (x_i - y_i)^2}
```

Le **voisinage ε** d’un point `x` est l’ensemble des points `y` tels que :
```math
d(x, y) \leq \varepsilon
```

---

## ⚙️ Fonctionnement mathématique

1. Pour chaque point, on regarde s’il a **assez de voisins** (≥ MinPts) dans un rayon ε.
2. Si oui, c’est un **noyau**, on crée un nouveau cluster.
3. On **étend le cluster** en ajoutant tous les voisins proches, et les voisins de ses voisins (récursivement).
4. Les points trop isolés sont marqués comme **bruit**.

---