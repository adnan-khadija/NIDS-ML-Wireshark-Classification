# 🛡️ Projet de Détection d'Intrusion Réseau (NIDS) basé sur Machine Learning

## 📝 Description du Projet

Ce projet est un Travail Pratique (TP) visant à implémenter et comparer deux modèles de classification (Random Forest et Arbre de Décision) pour la détection d'intrusions réseau. L'objectif est de distinguer le trafic réseau normal du trafic anormal (simulations d'attaques) à l'aide de données capturées via Wireshark.

### 🎯 Objectifs Principaux

* **Prétraitement de Données :** Transformer des captures brutes (paquets) en caractéristiques exploitables par un modèle ML.
* **Classification Binaire :** Entraîner des modèles à prédire si un paquet est `Normal (0)` ou `Anormal (1)`.
* **Évaluation Critique :** Analyser la performance (Accuracy, Precision, Recall) des modèles et identifier les biais (ex: dépendance aux adresses IP).

## ⚙️ Architecture et Données

Le laboratoire virtuel utilise une configuration de base pour simuler le trafic :

| Machine | Rôle | Adresse IP | Flux Généré |
| :--- | :--- | :--- | :--- |
| **Windows** | Cible | `192.168.194.129` | Normal et Cible d'Attaque |
| **Ubuntu 1** | Générateur Normal | `192.168.194.128` | SSH/TCP (Flux normal) |
| **Ubuntu 2** | Générateur Anormal | `192.168.194.130` | Attaques (Flux anormal) |

<img width="1208" height="583" alt="image" src="https://github.com/user-attachments/assets/9ebe4983-479d-4e95-bce3-43c5ab619c51" />


### Fichiers de Données

Les données utilisées pour l'entraînement sont des exportations de Wireshark au format CSV, basées sur la topologie ci-dessus :

* `normal.csv`: Contient les paquets de trafic normal (SSH, etc.).
* `anormal.csv`: Contient les paquets générés par les simulations d'attaques.

## Technologies et Librairies

Le projet est développé en Python et utilise les librairies scientifiques suivantes :

* **`pandas`**: Pour le chargement, la manipulation et le nettoyage des données CSV.
* **`scikit-learn` (sklearn)**: Pour l'implémentation des algorithmes ML (`DecisionTreeClassifier`, `RandomForestClassifier`), la séparation des données (`train_test_split`) et l'évaluation (`classification_report`, `confusion_matrix`).
* **`matplotlib` et `seaborn`**: Pour la visualisation des résultats (Matrice de Confusion, Importance des Features).

##  Installation et Exécution

### Prérequis

Python 3.x.

```bash
# Installation des librairies requises
pip install pandas scikit-learn matplotlib seaborn
