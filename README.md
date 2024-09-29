# Complétion de Matrices par Méthode d'Optimisation Alternée

---
Elyes KHALFALLAH - 5230635
---

## Description

Ce projet explore l'algorithme de **complétion de matrices** par **méthode d'optimisation alternée**. Le but est de compléter une matrice partiellement observée, en imposant des contraintes de faible rang sur la solution, en utilisant une approche itérative qui optimise successivement deux matrices de rang faible.

L'algorithme est appliqué à différents jeux de données, y compris le dataset **Iris**, et est évalué à travers plusieurs configurations d'hyperparamètres pour déterminer la meilleure combinaison permettant d'obtenir la meilleure reconstruction des données manquantes.

## Contenu du projet

Ce projet contient plusieurs étapes clés :

1. **Chargement des données** : Le dataset Iris est utilisé pour tester l'algorithme.
2. **Masquage des valeurs** : Un masque est appliqué aléatoirement pour cacher 10% des valeurs de la matrice.
3. **Algorithme d'optimisation alternée** : Un algorithme itératif qui optimise successivement les matrices $U$ et $V$.
4. **Tests d'hyperparamètres** : Différentes combinaisons de rang, régularisation Ridge, et taux de valeurs manquantes sont testées pour déterminer les meilleurs hyperparamètres.
5. **Évaluation** : Les résultats sont évalués à l'aide de l'erreur quadratique moyenne (RMSE) pour chaque combinaison d'hyperparamètres testée.

## Méthodologie

L'algorithme repose sur la minimisation de l'erreur de reconstruction uniquement sur les valeurs observées dans la matrice partiellement observée. La fonction à minimiser est :

$$
\min_{U, V} \sum_{(i,j) \in \Omega} (X_{ij} - (UV^T)_{ij})^2
$$

où $\Omega$ est l'ensemble des indices $(i,j)$ correspondant aux valeurs observées.

### Paramètres de l'algorithme :

- **Rank** : Le rang de la décomposition des matrices $U$ et $V$.
- **Alpha** : Le paramètre de régularisation Ridge appliqué pendant l'optimisation pour éviter les solutions extrêmes.
- **Max Iter** : Nombre maximal d'itérations pour l'optimisation alternée.
- **Tolerance** : Seuil de tolérance pour la convergence de l'algorithme.

## Installation et Prérequis

### Prérequis :

Ce projet utilise Python 3 et les bibliothèques suivantes :
- `pandas`
- `numpy`
- `matplotlib`
- `scikit-learn`

### Installation :

1. Clonez ce dépôt sur votre machine :
   ```bash
   git clone https://github.com/Bees11111/Projet-Optimisation.git
   ```
2. Dirigez vous vers le dossier :
   ```bash
   cd Projet-Optimisation
   ```
2. Créez un environnement virtuel nommé `env_opti` :
   ```bash
   python -m venv env_opti
   ```
2. Activez l'environnement virtuel :
   ```bash
   env_opti\Scripts\activate
   ```
2. Installez les dépendances :
   ```bash
   pip install -r requirements.txt
   ```

## Utilisation

Une fois le projet cloné et les dépendances installées, vous pouvez lancer les cellules du main.ipynb
