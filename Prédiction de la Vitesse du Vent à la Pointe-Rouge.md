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
│   ├── 01_regression_linéaire_simple(univariée).ipynb
│   ├── 02_Regression_linéaire_multivariée.ipynb
│   └── 03_MLPRegressor.ipynb
├── figures/         # Stocke les graphiques générés durant l'analyse
├── donnees/         # Contient les fichiers de données utilisés
│   ├── V_PR.xlsx
│   └── Marseille_régional.xlsx
│   └── Marseille_originale.xlsx
│   └── MPointerouge_originale.xlsx
└── README.md        # Ce fichier
```


## Données

Les principaux fichiers de données utilisés dans ce projet sont :

*   `donnees/V_PR.xlsx` : Contient les mesures de la vitesse du vent enregistrées à la Pointe-Rouge (variable cible).
*   `donnees/Marseille_régional.xlsx` : Contient les paramètres climatologiques régionaux enregistrés à Marseille, incluant la vitesse du vent, la température, l'humidité et la pression atmosphérique (variables prédictives).
## Exécution 
pour l'exécution de la méthode univariée, il suffit d'appuyer sur:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ZoubirCHATTI/Prediction-de-la-vitesse-du-vent/HEAD?filepath=notebooks/01_regression_lineaire_simple_univariee.ipynb)


pour l'éxécution de la méthode multivariée, il suffit d'appuyer sur:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ZoubirCHATTI/Prediction-de-la-vitesse-du-vent/HEAD?filepath=notebooks/02_Regression_lin%C3%A9aire_multivari%C3%A9e.ipynb)


pour l'éxécution de la méthode MLP, il suffit d'appuyer sur:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ZoubirCHATTI/Prediction-de-la-vitesse-du-vent/HEAD?filepath=notebooks/03_MLPRegressor.ipynb)



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

##**Conclusion**

Pour ce problème de prédiction du vent, la régression linéaire multivariée est le meilleur choix. Elle offre un bon équilibre entre simplicité, interprétabilité et précision prédictive. Le perceptron multicouche (MLP), bien que puissant, n’est pas vraiment nécessaire ici car les relations dans les données semblent largement linéaires.

**Auteur:** Zoubir CHATTI

