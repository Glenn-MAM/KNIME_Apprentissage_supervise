# 🍷 Prédiction de la Qualité du Vin : Analyse et Machine Learning avec KNIME

Bienvenue sur le dépôt de mon projet d'analyse de données et d'apprentissage supervisé. L'objectif de ce projet est de prédire la qualité d'un vin (sur une échelle de 3 à 8) en fonction de ses caractéristiques physico-chimiques, en utilisant la plateforme **KNIME Analytics**.

## 🎯 Contexte et Défi Principal : Le Déséquilibre des Classes

Avant même de modéliser, l'analyse exploratoire a mis en évidence un défi classique en Data Science : un jeu de données fortement déséquilibré (*Imbalanced Dataset*). 

<img width="1372" height="477" alt="Bar Chart Wine(Effectif)" src="https://github.com/user-attachments/assets/ef872f04-c847-4b88-989f-c41a5110fbfb" />
* Distribution des classes de qualité. L'écrasante majorité des vins sont notés 5 ou 6, rendant la détection des vins d'excellence (7 et 8) particulièrement complexe.*

## ⚙️ Méthodologie et Workflow

Pour répondre à ce problème tout en évitant les biais (comme la fuite de données ou le surapprentissage), j'ai construit un pipeline de bout en bout rigoureux :

<img width="895" height="490" alt="image" src="https://github.com/user-attachments/assets/89007904-fcc4-444f-bf4a-7b76f0e08c53" />


* Vue d'ensemble du processus de découverte de connaissances sous KNIME.*

**Points clés de l'architecture :**
* **Séparation stricte (Train/Test Split) :** 70% pour l'entraînement, 30% pour le test final afin de garantir une évaluation honnête.
* **Prévention du Data Leakage :** Modèle de normalisation (Min-Max) ajusté uniquement sur le jeu d'entraînement.
* **Optimisation des Hyperparamètres :** Recherche exhaustive (*Brute Force*) couplée à une **validation croisée à 10 plis (10-fold Cross-Validation)** pour éviter le surapprentissage.
* **Algorithmes comparés :** Random Forest, Arbre de Décision (Decision Tree) et K-Nearest Neighbors (KNN).

## 📊 Résultats et Évaluation

Une simple précision globale (Accuracy) étant trompeuse sur des données déséquilibrées, les modèles ont été évalués via des **Courbes ROC** et l'étude de l'Aire Sous la Courbe (AUC) pour des classes spécifiques.

<img width="1247" height="901" alt="image" src="https://github.com/user-attachments/assets/dd68a57e-d6a9-480d-bad5-cd0737b3fa8d" />

*Légende : Comparaison des performances (ROC) sur une classe majoritaire (Qualité 6).*

**Conclusion :** Le **Random Forest** s'impose comme le modèle le plus robuste, avec une AUC remarquable de **0.892** pour la détection des vins de qualité 7. L'arbre de décision, bien qu'un peu moins performant, offre une excellente explicabilité métier (règles de décision lisibles).

## 📄 Consulter le rapport complet

Pour une analyse plus détaillée incluant les matrices de confusion, les choix de prétraitement et les discussions sur le compromis performance/explicabilité, je vous invite à consulter mon rapport final :Rapport_KNIME.pdf

👉 **

🛠️ **Technologies utilisées :** Data Science, Machine Learning, KNIME, Cross-Validation, ROC/AUC.
