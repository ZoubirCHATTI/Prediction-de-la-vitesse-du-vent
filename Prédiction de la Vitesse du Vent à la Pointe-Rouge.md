# Prédiction de la Vitesse du Vent à la Pointe-Rouge

## Description

Ce projet vise à prédire la vitesse du vent à une micro-échelle (spécifiquement à la Pointe-Rouge) en utilisant des données climatiques régionales provenant de Marseille. L'objectif est d'évaluer et de comparer la performance de différents modèles de régression pour cette tâche de prédiction.

Trois approches de modélisation sont explorées et comparées :

1.  **Modèle Linéaire Univarié :** Un modèle simple basé sur une seule variable prédictive régionale.
2.  **Modèle Linéaire Multivarié :** Un modèle intégrant plusieurs variables climatiques régionales pour améliorer la prédiction.
3.  **Modèle Neuronal (MLP Regressor) :** Une approche basée sur un réseau de neurones (Perceptron Multi-Couches) pour capturer des relations potentiellement non-linéaires complexes entre les données régionales et la vitesse du vent locale.

L'analyse détaillée, l'exploration des données et l'implémentation de chaque modèle sont présentées dans des notebooks Jupyter dédiés.

## Structure du Projet

Le projet est organisé comme suit :

```
/
├── notebooks/       # Contient les notebooks Jupyter pour chaque étape d'analyse et modèle
│   ├── 1_exploration_modele_simple.ipynb
│   ├── 2_integration_multi_variables.ipynb
│   └── 3_approche_neuronale.ipynb
├── figures/         # Stocke les graphiques générés durant l'analyse
├── donnees/         # Contient les fichiers de données utilisés
│   ├── V_PR.xlsx
│   └── Marseille_régional.xlsx
└── README.md        # Ce fichier
```

*(Note : Les noms des notebooks sont supposés, veuillez les ajuster si nécessaire.)*

## Données

Les principaux fichiers de données utilisés dans ce projet sont :

*   `donnees/V_PR.xlsx` : Contient les mesures de la vitesse du vent enregistrées à la Pointe-Rouge (variable cible).
*   `donnees/Marseille_régional.xlsx` : Contient les paramètres climatologiques régionaux enregistrés à Marseille, incluant la vitesse du vent, la température, l'humidité et la pression atmosphérique (variables prédictives).
## Exécution 
pour l'exécution de la méthode univariée, il suffit d'appuyer sur:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ZoubirCHATTI/Prediction-de-la-vitesse-du-vent/HEAD?filepath=notebooks/01_regression_lineaire_simple_univariee.ipynb)

pour l'éxécution de la méthode multivariée, il suffit d'appuyer sur:

pour l'éxécution de la méthode MLP, il suffit d'appuyer sur:


## Modèles et Résultats

La performance des modèles est évaluée à l'aide de deux métriques principales :

*   **Coefficient de Détermination (R²)** : Indique la proportion de la variance de la variable cible qui est prévisible à partir des variables indépendantes.
*   **Erreur Quadratique Moyenne (MSE - Mean Squared Error)** : Mesure la moyenne des carrés des erreurs entre les valeurs prédites et les valeurs réelles.

Les résultats obtenus pour chaque modèle sont les suivants :

| Modèle                   | Coefficient de Détermination (R²) | Erreur Quadratique Moyenne (MSE) |
| :----------------------- | :-------------------------------: | :------------------------------: |
| Linéaire Simple (Univarié) | 0.957                             | 2.617                            |
| Linéaire Multivarié      | 0.961                             | 1.257                            |
| MLP Regressor (Neuronal) | 0.965                             | 2.209                            |

**Analyse des résultats :**

*   Le **modèle linéaire multivarié** présente la plus faible erreur (MSE = 1.257), suggérant une meilleure adéquation globale aux données par rapport au modèle univarié simple.
*   Le **modèle MLP Regressor** obtient le coefficient de détermination le plus élevé (R² = 0.965), indiquant qu'il explique la plus grande proportion de la variance de la vitesse du vent locale, bien que son erreur soit intermédiaire.
*   Le **modèle linéaire simple** sert de référence de base, surpassé par les deux autres approches plus complexes.

## Instructions d'Utilisation

Pour explorer les analyses et exécuter les modèles :

1.  **Téléchargez le projet :** Clonez ou téléchargez le contenu de ce dépôt GitHub, en vous assurant d'inclure les dossiers `notebooks/` et `donnees/`.

    ```bash
    git clone <URL_DU_DEPOT_GIT>
    cd <NOM_DU_DOSSIER_PROJET>
    ```

2.  **Ouvrez un Notebook :** Lancez votre environnement Jupyter (Jupyter Notebook, JupyterLab, Google Colab, VS Code, etc.) et ouvrez l'un des notebooks situés dans le dossier `notebooks/`.

3.  **Configurez les Chemins d'Accès :** Avant d'exécuter les cellules, assurez-vous que les chemins d'accès aux fichiers de données (`.xlsx` dans le dossier `donnees/`) sont correctement configurés dans les notebooks pour correspondre à leur emplacement sur votre machine ou dans votre environnement d'exécution.

4.  **Exécutez les Cellules :** Exécutez les cellules du notebook séquentiellement pour reproduire l'analyse, l'entraînement des modèles et l'évaluation des performances.

