# Exploratory Data Analysis of Coffee Store Sales

## 📌 Project Overview
Raw sales data often contain errors, inconsistencies, and missing values, which limit their usefulness for analysis and decision-making.  
This project focuses on transforming a **dirty coffee store sales dataset** into a **clean, consistent, and reliable dataset**, followed by an exploratory analysis and the creation of actionable business insights.

---

## 🎯 Project Objectives
- Clean and structure raw sales data  
- Identify and handle missing and inconsistent values  
- Reconstruct essential missing information using logical rules  
- Produce clear insights to support business decisions  
- Prepare the dataset for dashboard creation  

---

## 📊 Dataset Description

### Source
- Simulated dataset from Kaggle  
- Dirty Café Sales Dataset  

### Main Variables
- **Item**
- **Quantity**
- **Price Per Unit**
- **Total Spent**
- **Payment Method**
- **Location**
- **Transaction Date**

### Identified Data Issues
- Missing values  
- Inconsistent values (`ERROR`, `UNKNOWN`)  
- Logical inconsistencies between *Quantity*, *Price Per Unit*, and *Total Spent*  

---

## 🛠️ Tools Used
- **Microsoft Excel 2019**

---

## 🧹 Data Cleaning Methodology
The data cleaning process was conducted in a **progressive and systematic manner**, handling variables from the simplest to the most complex to ensure overall consistency and reliability.

### 1. Handling Categorical Variables

#### Payment Method
- Empty cells and values labeled `ERROR` or `UNKNOWN` were replaced with **"Not mentioned"**
- This approach ensures transparency while avoiding unreliable assumptions

#### Location
- The same treatment was applied
- Missing or erroneous values were replaced with **"Not mentioned"**

**Fonction used:** Find and Replace (Ctrl + H)

---

### 2. Handling Transaction Dates
- The *Transaction Date* column contained **460 missing or erroneous values**
- Due to the absence of external information, these values were left empty to avoid biased time-based analysis

---

### 3. Reconstruction of Sales-Related Numerical Variables
The following mathematical relationships were used:

- **Total Spent = Price Per Unit × Quantity**
- **Price Per Unit = Total Spent ÷ Quantity**
- **Quantity = Total Spent ÷ Price Per Unit**

Temporary calculation errors (`#VALUE!`, `#DIV/0!`) appeared when information was missing simultaneously and were resolved progressively as other columns were reconstructed.

---

### 4. Deduction of Unit Prices from Products
Using complete observations in the dataset, the following unit prices were inferred:

| Product    | Unit Price ($) |
|------------|----------------|
| Cookie     | 1.0            |
| Tea        | 1.5            |
| Coffee     | 2.0            |
| Cake       | 3.0            |
| Juice      | 3.0            |
| Sandwich   | 4.0            |
| Smoothie   | 4.0            |
| Salad      | 5.0            |

Missing unit prices were filled accordingly.

---

### 5. Handling Ambiguities and Residual Issues
Some ambiguities remained due to:
- Missing product names
- Different products sharing the same unit price

To resolve this:
- Products were grouped temporarily (e.g. *Cake/Juice*, *Sandwich/Smoothie*)
- Cross-checks between *Item* and *Price Per Unit* allowed identification of the most likely product

Orders with irrecoverable essential information were excluded from the analysis.

---

### 6. Final Data Validation
At the end of the cleaning process:
- All quantitative relationships were respected  
- Calculation errors were eliminated  
- Remaining missing values correspond only to unrecoverable information  

✅ **Final dataset:** 9,992 valid orders  
The dataset is now clean, consistent, and ready for analysis and dashboard creation.

---

## 📈 Key Performance Overview
- **Total orders:** 9,992  
- **Total products sold:** 30,260  
- **Total revenue:** $89,319.50  
- **Average Order Value (AOV):** $2.95  

This reflects frequent transactions with relatively low individual value.

---

## 🥗 Product Performance Insights
- **Highest revenue product:** Salad ($19,145)  
- **Lowest revenue product:** Cookie ($3,603)

### Most Frequently Ordered Products
- Coffee (3,929 orders)  
- Salad (3,829 orders)  
- Tea (3,655 orders)

### Least Frequently Ordered Products
- Smoothie (3,346 orders)  
- Sandwich (3,449 orders)  
- Cake (3,473 orders)

➡️ This highlights the difference between **high-volume products** and **high-revenue contributors**.

---

## 📅 Temporal Trends
### Revenue by Month
- Highest revenue months:
  - June ($7,363)
  - October ($7,334)
  - January ($7,304)
- Lowest revenue month:
  - February ($6,644)

### Sales Volume
- Most active month: October (2,544 orders)  
- Least active month: February (2,253 orders)  

Possible seasonal effects are observed.

---

## 💳 Payment Method Distribution
- **Digital Wallet** was the most used payment method (2,290 orders)
- Interpretation is limited by a high number of transactions labeled **"Not mentioned"** (3,175 orders)

---

## 📍 Location Distribution
- Takeaway: 3,021 orders  
- In-store: 3,013 orders  
- Not mentioned: 3,985 orders  

Results should be interpreted cautiously due to missing location data.

---

## ✅ Recommendations

### 1. Capitalize on High-Revenue Products
- Promote salad-based products through targeted campaigns  
- Ensure consistent stock availability to avoid missed sales  

### 2. Leverage High-Volume Products
- Apply upselling strategies (larger sizes, premium options)  
- Test moderate price increases on Coffee and Tea  

### 3. Boost Sales During Low-Activity Periods
- Introduce seasonal promotions in February  
- Implement loyalty programs to encourage repeat visits  

---

# Analyse et visualisation des ventes d’un Coffee Store

## 📌 Présentation du projet
Les données de ventes brutes contiennent souvent des erreurs, des incohérences et des valeurs manquantes, rendant leur exploitation difficile.  
Ce projet vise à transformer un **jeu de données non nettoyé** en un **outil d’aide à la décision fiable**, à travers un processus rigoureux de nettoyage des données, une analyse exploratoire et une visualisation claire des performances commerciales.

---

## 🎯 Objectifs du projet
- Nettoyer et structurer les données de ventes  
- Traiter les valeurs manquantes et incohérentes  
- Reconstituer les informations essentielles à partir de règles logiques  
- Préparer un jeu de données exploitable pour la création d’un dashboard synthétique  

---

## 📊 Description du jeu de données

### Source
- Données simulées provenant de Kaggle  
- Dataset : *Dirty Café Sales*  

### Variables principales
- **Item** (produit)
- **Quantity** (quantité vendue)
- **Price Per Unit** (prix unitaire)
- **Total Spent** (montant total dépensé)
- **Payment Method** (méthode de paiement)
- **Location**
- **Transaction Date** (date de transaction)

### Problèmes identifiés
- Valeurs manquantes  
- Valeurs incohérentes (`ERROR`, `UNKNOWN`)  
- Incohérences logiques entre quantité, prix unitaire et montant total  

---

## 🛠️ Outil utilisé
- **Microsoft Excel 2019**

---

## 🧹 Méthodologie de nettoyage des données
Le nettoyage a été réalisé de manière **progressive et méthodique**, en traitant les colonnes du plus simple au plus complexe afin de garantir la cohérence et la fiabilité du jeu de données final.

---

### 1. Traitement des variables catégorielles

#### Payment Method
- Les cellules vides ainsi que celles contenant `ERROR` ou `UNKNOWN` ont été remplacées par **« Not mentioned »**
- Ce choix permet de conserver la transparence tout en évitant des reconstructions non fiables

#### Location
- La même approche a été appliquée
- Les valeurs manquantes ou erronées ont été remplacées par **« Not mentioned »**

**Fonction utilisée :** Rechercher / Remplacer (Ctrl + H)

---

### 2. Gestion des dates de transaction
- La colonne *Transaction Date* contenait **460 valeurs manquantes ou erronées**
- En l’absence d’informations externes fiables, ces cellules ont été laissées vides afin d’éviter toute imputation arbitraire pouvant biaiser les analyses temporelles

---

### 3. Reconstitution des variables numériques liées aux ventes
Les colonnes **Quantity**, **Price Per Unit** et **Total Spent** sont liées par des relations mathématiques simples :

- **Total Spent = Price Per Unit × Quantity**
- **Price Per Unit = Total Spent ÷ Quantity**
- **Quantity = Total Spent ÷ Price Per Unit**

Des erreurs temporaires (`#VALEUR!`, `#DIV/0!`) sont apparues lorsque plusieurs informations étaient manquantes simultanément.  
Elles ont été corrigées progressivement à mesure que les autres colonnes étaient reconstruites.

---

### 4. Déduction des prix unitaires à partir des produits
À partir des observations complètes du jeu de données, les prix unitaires suivants ont été déduits :

| Produit     | Prix unitaire ($) |
|-------------|-------------------|
| Cookie      | 1.0               |
| Tea         | 1.5               |
| Coffee      | 2.0               |
| Cake        | 3.0               |
| Juice       | 3.0               |
| Sandwich    | 4.0               |
| Smoothie    | 4.0               |
| Salad       | 5.0               |

Les valeurs manquantes de la colonne **Price Per Unit** ont été complétées en conséquence.

---

### 5. Gestion des ambiguïtés et valeurs résiduelles
Certaines incohérences persistaient en raison :
- de valeurs manquantes dans la colonne *Item* ;
- de produits partageant le même prix unitaire (Cake/Juice, Sandwich/Smoothie).

Pour résoudre ces cas :
- des libellés temporaires combinés ont été utilisés ;
- un croisement entre *Item* et *Price Per Unit* a permis d’identifier le produit le plus probable.

Les commandes pour lesquelles aucune reconstitution fiable n’était possible ont été exclues de l’analyse.

---

### 6. Validation finale du nettoyage
À l’issue du processus :
- toutes les relations quantitatives entre variables sont respectées ;
- les erreurs de calcul ont été éliminées ;
- les valeurs manquantes restantes correspondent uniquement à des informations impossibles à reconstituer.

✅ **Jeu de données final : 9 992 commandes**  
Le dataset est désormais cohérent, exploitable et prêt pour l’analyse et la création d’un dashboard.

---

## 📈 Vue d’ensemble des performances clés
- **Nombre total de commandes :** 9 992  
- **Produits vendus :** 30 260  
- **Chiffre d’affaires total :** 89 319,5 $  
- **Valeur moyenne d’une commande (AOV) :** 2,95 $  

Ces résultats reflètent des transactions fréquentes mais de faible montant.

---

## 🥗 Analyse de la performance des produits
- **Produit le plus rentable :** Salad (19 145 $)
- **Produit le moins rentable :** Cookie (3 603 $)

### Produits les plus commandés
- Coffee (3 929 commandes)
- Salad (3 829 commandes)
- Tea (3 655 commandes)

### Produits les moins commandés
- Smoothie (3 346 commandes)
- Sandwich (3 449 commandes)
- Cake (3 473 commandes)

➡️ Ces résultats mettent en évidence la différence entre **produits à fort volume** et **produits à forte contribution au chiffre d’affaires**.

---

## 📅 Tendances temporelles
### Chiffre d’affaires mensuel
- Mois les plus performants :
  - Juin (7 363 $)
  - Octobre (7 334 $)
  - Janvier (7 304 $)
- Mois le moins performant :
  - Février (6 644 $)

### Volume de ventes
- Mois le plus actif : Octobre (2 544 commandes)
- Mois le moins actif : Février (2 253 commandes)

Un effet de saisonnalité est suggéré.

---

## 💳 Répartition des méthodes de paiement
- Le **Digital Wallet** est la méthode la plus utilisée (2 290 commandes)
- L’analyse est limitée par un nombre important de transactions **non renseignées** (3 175 commandes)

---

## 📍 Répartition par localisation
- Takeaway : 3 021 commandes
- In-store : 3 013 commandes
- Not mentioned : 3 985 commandes

Les résultats doivent être interprétés avec prudence en raison du volume élevé de données manquantes.

---

## ✅ Recommandations

### 1. Capitaliser sur les produits à forte contribution
- Mettre en avant les produits à base de salade via des promotions ciblées
- Garantir une disponibilité constante pour éviter les ruptures de stock

### 2. Exploiter les produits à fort volume
- Proposer des stratégies d’upsell (formats plus grands, options premium)
- Tester des augmentations de prix modérées sur Coffee et Tea

### 3. Dynamiser les périodes creuses
- Lancer des promotions saisonnières en février
- Mettre en place des programmes de fidélité pour stimuler les visites récurrentes

---
