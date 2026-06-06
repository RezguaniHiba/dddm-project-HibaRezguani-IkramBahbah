# 🛒 Projet BI E-commerce Olist — Data-Driven Decision Making

> **Module : Data-Driven Decision Making | ENSIAS — Génie Logiciel | 2025-2026**

> Réalisé par : **REZGUANI Hiba** & **BAHBAH Ikram** | Encadré par : **Prof. Youness TABII**

---

## 📌 Table des Matières

1. [Domaine Métier](#1--domaine-métier)
2. [Problématique Métier & Question Décisionnelle](#2--problématique-métier--question-décisionnelle)
3. [KPIs Primaires & Secondaires](#3--kpis-primaires--secondaires)
4. [KPI Tree Hiérarchique](#4--kpi-tree-hiérarchique)
5. [Business Case & ROI](#5--business-case--roi)
6. [Architecture du Projet](#6--architecture-du-projet)
7. [Dashboards Power BI](#7--dashboards-power-bi)
8. [Modèles de Machine Learning](#8--modèles-de-machine-learning)
9. [A/B Test Plan](#9--ab-test-plan)
10. [Installation & Lancement](#10--installation--lancement)

---

## 1 — Domaine Métier

**Domaine : E-Commerce & Business Intelligence**

Ce projet s'inscrit dans le domaine du **e-commerce** et de la **Business Intelligence**.

**Olist** est une marketplace e-commerce brésilienne permettant à de nombreux vendeurs de commercialiser leurs produits à travers différentes régions du Brésil.

L'objectif est d'exploiter les données transactionnelles, clients, produits et logistiques pour améliorer :
- la performance commerciale
- la compréhension du comportement client
- l'efficacité logistique
- la prise de décision stratégique

**Sources de données utilisées (Kaggle — Brazilian E-Commerce Public Dataset by Olist) :**

| Fichier | Contenu | Volume |
|---------|---------|--------|
| `olist_orders_dataset.csv` | Commandes (statut, dates) | ~100K lignes |
| `olist_order_items_dataset.csv` | Produits, prix, frais de livraison | ~113K lignes |
| `olist_customers_dataset.csv` | Clients, villes, régions | ~100K lignes |
| `olist_products_dataset.csv` | Catalogue produits, catégories | ~33K lignes |
| `olist_order_reviews_dataset.csv` | Avis clients (1–5 étoiles) | ~100K lignes |
| `olist_order_payments_dataset.csv` | Modes et valeurs de paiement | ~100K lignes |

> 📦 Dataset : [Brazilian E-Commerce Public Dataset by Olist — Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

---

## 2 — Problématique Métier & Question Décisionnelle

### ❓ Question Décisionnelle Centrale

> **"Comment optimiser les ventes, améliorer l'expérience client et réduire les inefficacités logistiques grâce à l'analyse des données e-commerce ?"**

Cette problématique se décline selon trois profils utilisateurs :

### 🎯 Direction
- Quelle est la performance globale de l'entreprise ?
- Comment évoluent les ventes et le chiffre d'affaires ?
- Quelles régions ou catégories contribuent le plus à la performance ?

### 📣 Marketing
- Quels segments clients sont les plus rentables ?
- Quelles villes génèrent le plus de valeur ?
- Comment évolue le comportement d'achat des clients ?

### 🚚 Opérations / Logistique
- Quelles régions présentent les plus grands délais ou retards ?
- Comment optimiser les frais de livraison ?
- Où les livraisons sont-elles les plus concentrées ?

---

## 3 — KPIs Primaires & Secondaires

### 📊 KPIs Stratégiques Primaires

| KPI | Description | Objectif |
|------|-------------|-----------|
| Chiffre d'affaires total | Revenus générés par l'ensemble des ventes réalisées sur la plateforme. | Mesurer la performance commerciale globale. |
| Nombre de commandes | Volume total des commandes effectuées par les clients. | Suivre l'activité commerciale et l'évolution des ventes. |
| Panier moyen | Valeur moyenne dépensée par commande. | Évaluer le comportement d'achat des clients. |
| Nombre de clients | Nombre total de clients ayant effectué au moins une commande. | Mesurer la croissance et la portée de la clientèle. |
| Nombre de produits vendus | Quantité totale de produits commercialisés. | Évaluer la demande et la performance des produits. |
| Taux de livraison | Pourcentage des commandes livrées avec succès. | Mesurer l'efficacité et la qualité des opérations logistiques. |

### 📊 KPIs Secondaires

| KPI | Description |
|------|-------------|
| Fréquence d'achat | Nombre moyen d'achats effectués par client sur la période analysée. |
| Valeur moyenne client | Chiffre d'affaires moyen généré par chaque client. |
| Coût total de livraison | Montant total des frais de livraison supportés pour l'ensemble des commandes. |
| Coût moyen de livraison | Coût moyen de livraison par commande. |
| Délai moyen de livraison | Temps moyen écoulé entre la commande et la réception par le client. |
| Retard moyen | Écart moyen entre la date de livraison estimée et la date réelle de livraison. |
| CA par région | Répartition du chiffre d'affaires selon les différentes régions géographiques. |
| CA par ville | Répartition du chiffre d'affaires selon les villes. |
| CA par catégorie | Chiffre d'affaires généré par chaque catégorie de produits. |
| Nombre de villes actives | Nombre de villes ayant enregistré au moins une commande. |
| Nombre de régions | Nombre de régions couvertes par l'activité e-commerce. |
| Nombre de catégories | Nombre de catégories de produits disponibles et analysées. |

---

## 4 — KPI Tree Hiérarchique

# 🎯 KPI Tree

## Objectif stratégique principal
**Augmenter la performance globale du e-commerce Olist**

### 💰 Axe 1 — Performance Commerciale
- Chiffre d'affaires total
- Nombre de commandes
- Panier moyen
- Évolution mensuelle des ventes

### 👥 Axe 2 — Performance Client
- Nombre de clients
- Fréquence d'achat
- Valeur moyenne client
- Panier moyen par ville

### 📦 Axe 3 — Performance Produit
- Nombre de produits vendus
- Chiffre d'affaires par catégorie
- Catégories les plus performantes
- Prix moyen produit

### 🚚 Axe 4 — Performance Logistique
- Taux de livraison
- Délai moyen de livraison
- Retard moyen
- Coût total de livraison
- Coût moyen de livraison

### 🗺️ Axe 5 — Analyse Géographique
- Chiffre d'affaires par région
- Chiffre d'affaires par ville
- Nombre de villes actives
- Concentration géographique des livraisons

---

## 5 — Business Case & ROI

### 📋 Situation Actuelle

L'entreprise dispose d'un volume important de données e-commerce dispersées entre plusieurs dimensions : commandes, clients, produits, régions, livraisons, frais logistiques.

Sans outil décisionnel centralisé, il est difficile de :
- suivre la performance commerciale en temps réel
- identifier les segments clients rentables
- piloter la qualité logistique par région
- détecter les catégories sous-performantes

### 💡 Solution Proposée

| Composant | Détail |
|-----------|--------|
| Pipeline ETL | Nettoyage, transformation, intégration et enrichissement des données issues des fichiers CSV Olist. |
| Dataset consolidé | Dataset unifié et préparé pour l'analyse décisionnelle et les modèles de Machine Learning. |
| Dashboard Power BI | Tableau de bord interactif structuré autour de trois profils décisionnels : Direction, Marketing et Opérations. |
| Modèles de Machine Learning | Trois modèles analytiques : prévision des ventes, segmentation clients RFM et prédiction de la satisfaction client avec interprétabilité SHAP. |
| A/B Test Plan | Protocole expérimental conçu pour évaluer l'impact d'actions métier et valider les recommandations issues de l'analyse des données. |

### 📈 Valeur Métier

| Profil | Valeur apportée |
|--------|----------------|
| **Direction** | Vision globale, pilotage du CA, tendances temporelles |
| **Marketing** | segmentation et ciblage clients |
| **Opérations** | Optimisation des délais et des coûts logistiques par région |

### 💰 ROI Attendu

| Levier | Mécanisme | Impact estimé |
|--------|-----------|--------------|
| Réactivation des clients perdus | Mise en place de campagnes marketing ciblées sur le segment identifié par l'analyse RFM afin d'encourager les anciens clients à effectuer de nouveaux achats. | Augmentation du chiffre d'affaires grâce au retour d'une partie des clients inactifs. |
| Optimisation logistique | Réduction des coûts de livraison grâce à l'identification des régions les moins performantes et à l'amélioration de la planification logistique. | Diminution des dépenses opérationnelles liées aux livraisons. |
| Amélioration de la satisfaction client | Utilisation du modèle prédictif pour détecter les clients à risque d'insatisfaction et intervenir avant qu'un avis négatif ne soit publié. | Réduction des réclamations et amélioration de la fidélisation client. |
| A/B Testing sur les frais de livraison | Expérimentation de différentes politiques de frais de livraison afin d'évaluer leur impact sur le taux de conversion et les ventes. | Impact mesuré expérimentalement avant déploiement à grande échelle. |

> **Le ROI attendu représente le gain potentiel obtenu grâce à l'exploitation des analyses décisionnelles, des modèles de Machine Learning et des recommandations métier issues du projet.**

---

## 6 — Architecture du Projet

```
┌──────────────────────────────────────────────────────┐
│              SOURCES DE DONNÉES (Kaggle)             │
│          7 fichiers CSV — Olist Dataset              │
└─────────────────────┬────────────────────────────────┘
                      │
                      ▼
┌──────────────────────────────────────────────────────┐
│           PIPELINE ETL — Python / Pandas             │
│   Nettoyage · Jointures · Feature Engineering       │
└──────────┬────────────────────────┬─────────────────┘
           │                        │
           ▼                        ▼
┌────────────────────┐   ┌──────────────────────────┐
│  MACHINE LEARNING  │   │  DASHBOARDS — Power BI   │
│                    │   │                          │
│  Modèle 1          │   │  Vue Direction           │
│  Prévision Ventes  │   │  Vue Marketing           │
│  (Régression)      │   │  Vue Opérations          │
│                    │   └──────────────────────────┘
│  Modèle 2          │  
│  Segmentation RFM  │   
│  (Clustering)      │
│                    │
│  Modèle 3          │
│  Satisfaction      │
│  (Classification)  │
└────────────────────┘
           │
           ▼
┌──────────────────────────────────────────────────────┐
│           DÉCISION & A/B TESTING                     │
│   3 Recommandations actionnables + Plan expérimental │
└──────────────────────────────────────────────────────┘
```

---

## 7 — Dashboards Power BI

Le fichier `.pbix` contient **5 vues interactives** avec filtres croisés (Année, Région, Ville, Statut commande) :

| Vue | Profil cible | Contenu principal |
|-----|-------------|------------------|
| **Vue Direction** | Direction générale | Chiffre d'affaires total,Nombre de commandes, panier moyenne ,Évolution des ventes et tendances temporelles |
| **Analyse des Clients et des Ventes** (Vue Marketing) | Équipe Marketing | Nombre de clients, Valeur moyenne client, Fréquence d'achat, Analyse par ville, Analyse géographique|
| **Logistique & Performance des Livraisons** (Vue Opérations) | Équipe Logistique | Coût total de livraison, Coût moyen de livraison, Délai moyen de livraison, Retard moyenn Répartition géographique des livraisons |

### 🚀 Lancement du Dashboard

**Prérequis :** Power BI Desktop ([télécharger ici](https://powerbi.microsoft.com/desktop/))

```
1. Ouvrir Power BI Desktop
2. File → Open → dashboard/Olist_Dashboard.pbix
3. Actualiser les données si besoin (Home → Refresh)
```

---

## 8 — Modèles de Machine Learning
Trois modèles ont été développés afin d'apporter une dimension prédictive au système décisionnel.
### Modèle 1 — Prévision des Ventes
**Fichier :** `notebooks/Modele1_Prevision_Ventes_v2.ipynb`

- **Type :** Régression supervisée
- **Objectif :** Prédire le chiffre d'affaires futur à partir des données historiques de ventes afin d'anticiper les tendances commerciales et d'améliorer la planification stratégique.
- **Algorithmes comparés :** Régression Linéaire (baseline), Random Forest Regressor et XGBoost Regressor.
- **Métriques :** RMSE (Root Mean Squared Error), MAE (Mean Absolute Error) et R² (Coefficient de Détermination).
- **Features :** année, mois, région, nombre de commandes, nombre de clients, panier moyen, coût de livraison, délai moyen de livraison et catégories de produits.
- **Interprétabilité :** Importance des variables et analyse SHAP pour expliquer l'influence de chaque caractéristique sur les prévisions.
- **Valeur métier :** Permet d'anticiper l'évolution du chiffre d'affaires, d'optimiser les décisions budgétaires et d'adapter les stratégies commerciales en fonction des tendances prédites.

---

### Modèle 2 — Segmentation Clients RFM
**Fichier :** `notebooks/Modele2_SegmentationClients_RFM.ipynb`

- **Type :** Clustering non supervisé
- **Objectif :** Identifier des groupes homogènes de clients afin d'adapter les stratégies marketing et d'améliorer la fidélisation.
- **Méthodologie :** Analyse RFM (Récence, Fréquence, Montant) suivie d'un clustering K-Means.
- **Algorithme :** K-Means avec sélection du nombre optimal de clusters à l'aide de la méthode du coude (Elbow Method) et du score de silhouette.
- **Variables utilisées :**
  - **Récence (Recency)** : nombre de jours depuis le dernier achat du client.
  - **Fréquence (Frequency)** : nombre total de commandes effectuées par le client.
  - **Montant (Monetary)** : montant total dépensé par le client.

#### Analyse RFM

L'analyse RFM permet d'évaluer la valeur et l'engagement des clients à travers trois dimensions :

- **Récence (R)** : plus un client a acheté récemment, plus il est susceptible de revenir.
- **Fréquence (F)** : les clients qui achètent régulièrement sont généralement plus fidèles.
- **Montant (M)** : les clients qui dépensent davantage contribuent plus fortement au chiffre d'affaires.

Cette approche permet de mieux comprendre les comportements d'achat et de construire des actions marketing ciblées.
#### Segments identifiés

| Segment | Caractéristiques principales | Action recommandée |
|----------|-----------------------------|-------------------|
| **Clients Fidèles** | Achètent plus fréquemment que les autres clients et génèrent une valeur élevée. | Programmes de fidélité, offres exclusives et récompenses VIP. |
| **Gros Acheteurs** | Dépensent le plus et constituent le segment ayant la plus forte contribution au chiffre d'affaires. | Fidélisation, recommandations personnalisées et stratégies de cross-selling. |
| **Nouveaux Acheteurs** | Clients récents avec un faible historique d'achat et un montant dépensé relativement faible. | Campagnes d'engagement, offres de bienvenue et recommandations personnalisées. |
| **Clients Perdus** | Clients inactifs depuis une longue période avec un faible niveau d'engagement. | Campagnes de réactivation, promotions ciblées et offres de retour. |

---

### Modèle 3 — Prédiction de la Satisfaction Client
**Fichier :** `notebooks/Modele3_Prediction_Satisfaction_Client.ipynb`

### Modèle 3 — Prédiction de la Satisfaction Client

- **Type :** Classification supervisée binaire
- **Objectif :** Prédire si un client sera satisfait (**review score ≥ 4**) ou insatisfait (**review score ≤ 3**) après une commande, afin d'anticiper les avis négatifs et mettre en place des actions préventives.
- **Algorithmes comparés :** Régression Logistique (baseline), Random Forest Classifier et XGBoost Classifier.
- **Métriques d'évaluation :** Accuracy, F1-Score, Precision, Recall et ROC-AUC.
- **Features :** délai réel de livraison, retard par rapport à la date estimée, délai d'approbation de la commande, nombre d'articles commandés, revenu total de la commande, prix moyen des articles, type de paiement, nombre de versements, heure/jour/mois d'achat et localisation géographique du client.
- **Interprétabilité :** Analyse SHAP globale et locale pour identifier les facteurs ayant le plus d'impact sur la satisfaction client.
- **Valeur métier :**
  - Identifier les clients à risque avant la publication d'un avis négatif.
  - Détecter les problèmes logistiques influençant l'expérience client.
  - Suivre la satisfaction prédite comme indicateur avancé de performance.
    
---

## 9 — A/B Test Plan

**Hypothèse :** Une réduction de 30% des frais de livraison augmente-t-elle significativement le nombre de commandes, le panier moyen et le taux de conversion ?

| Paramètre | Groupe A (contrôle) | Groupe B (test) |
|-----------|--------------------|-----------------| 
| Condition | Frais standards | -30% sur frais de livraison |
| Taille | 5 000 clients | 5 000 clients |
| Assignation | Aléatoire équilibrée | |
| Durée | 2 à 4 semaines | |
| Test statistique | t-test de Student (p-value < 0,05) | |

**KPIs suivis :**
- Nombre de commandes, CA, panier moyen, taux de conversion *(commerciaux)*
- Coût moyen de livraison, délai moyen *(logistiques)*
- Satisfaction client, taux de réclamation *(expérience client)*

**Décision :**
- Si groupe B significativement meilleur → adoption de la réduction des frais
- Sinon → maintien de la politique actuelle

📄 **Document complet :** [`docs/AB_Test_Plan.pdf`](docs/AB_Test_Plan.pdf)

---

## 10 — Installation & Lancement

### Prérequis

```
Python >= 3.9
Power BI Desktop (pour les dashboards .pbix)
Git
```

### Installation

```bash
# 1. Cloner le dépôt
git clone https://github.com/RezguaniHiba/dddm-project-HibaRezguani-IkramBahbah
cd dddm-project-HibaRezguani-IkramBahbah

# 2. Créer un environnement virtuel
python -m venv venv
source venv/bin/activate        # Linux / Mac
venv\Scripts\activate           # Windows

# 3. Installer les dépendances Python
pip install -r requirements.txt

# 4. Télécharger le dataset Olist
#    → https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce
#    → Placer les fichiers CSV dans data/raw/

# 5. Lancer Jupyter
jupyter notebook notebooks/
```

### Ordre d'exécution des Notebooks

```
1. notebooks/00_ETL_Audit_DataDictionary.ipynb               ← Pipeline ETL + Audit + Data Dictionary
2. notebooks/Modele1_Prevision_Ventes_v2.ipynb               ← Régression
3. notebooks/Modele2_SegmentationClients_RFM.ipynb           ← Clustering RFM
4. notebooks/Modele3_Prediction_Satisfaction_Client.ipynb    ← Classification
```

---
