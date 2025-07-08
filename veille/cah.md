# 🧠 Classification Ascendante Hiérarchique (CAH) : Mathématiques et fonctionnement

## 🔍 Objectif

Créer une hiérarchie de clusters sans spécifier à l'avance leur nombre.  
Chaque observation commence dans son propre cluster, puis des paires de clusters sont **fusionnées** progressivement selon leur **ressemblance**.

---

## ⚙️ Fonctionnement mathématique

### 1. Calcul des distances entre points

Première étape : mesurer **à quel point les points sont proches** les uns des autres.

➡️ **Distance euclidienne** (souvent utilisée) :

```math
d(x, y) = \sqrt{\sum_{i=1}^{n} (x_i - y_i)^2}
```

Cela donne une **matrice de distances** entre tous les points.

---

### 2. Fusion des clusters

On fusionne à chaque étape les **deux clusters les plus proches**.

> La notion de "proximité" entre deux **groupes** dépend du **critère de liaison** (*linkage*).

### 🔗 Méthodes de liaison :

- **Single linkage** : plus petite distance entre deux points de deux groupes
- **Complete linkage** : plus grande distance entre deux points
- **Average linkage** : moyenne des distances
- **Ward** (le plus utilisé) : minimise l’**inertie intra-cluster**

---

### 3. Construction de la hiérarchie

À chaque fusion, on construit une **arborescence** (*dendrogramme*) qui montre comment les clusters se regroupent.

La fusion continue jusqu’à ce qu’on ait **un seul cluster** contenant tous les points.

---

## 📉 Fonction de Ward (cas particulier)

L’approche de **Ward** cherche à **minimiser la somme des carrés des distances** à l’intérieur des clusters (inertie).

À chaque étape, on choisit de fusionner les deux clusters dont la fusion **augmente le moins** l’inertie :

```math
\Delta E = \frac{n_A \cdot n_B}{n_A + n_B} ||C_A - C_B||^2
```

- `n_A`, `n_B` = tailles des clusters
- `C_A`, `C_B` = centres des clusters

---