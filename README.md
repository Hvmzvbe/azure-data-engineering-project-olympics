# 🏅 Azure Olympic Data Pipeline – Low-Code Data Engineering Project

## 📘 Description du projet
Ce projet illustre la mise en place d’un **pipeline de données Low-Code sur Azure** pour le traitement, la transformation et la visualisation des données des **Jeux Olympiques**.  
Il combine **Azure Data Factory**, **Azure Data Lake Gen2**, **Azure Databricks**, **Azure Synapse Analytics**, et **Power BI** pour construire une architecture moderne et évolutive.

---

## 🎯 Objectifs
- Ingestion automatique de fichiers CSV (Athletes, Teams, Coaches, Medals, EntriesGender) via **Azure Data Factory**
- Stockage des données brutes et transformées dans **Azure Data Lake Storage Gen2**
- Nettoyage et transformation avec **Azure Databricks (PySpark)**
- Analyse et modélisation des données via **Azure Synapse Analytics**
- Création de tableaux de bord interactifs avec **Power BI**

---

## 🏗️ Architecture du projet
<img width="1917" height="588" alt="ARpr" src="https://github.com/user-attachments/assets/03b43b28-e6ca-4f63-99a9-933406c2266d" />


### Étapes principales :
1. **Data Source** → fichiers CSV contenant les données olympiques
2. **Data Factory** → pipeline d’ingestion automatisé
3. **Data Lake Gen2 (Raw Layer)** → stockage brut
4. **Azure Databricks** → nettoyage, normalisation et enrichissement
5. **Data Lake Gen2 (Transformed Layer)** → stockage des données nettoyées
6. **Azure Synapse Analytics** → analyse et intégration vers Power BI
7. **Power BI / Looker Studio / Tableau** → visualisation et exploration

---

## ⚙️ Étapes du pipeline

### 🔹 Ingestion (ADF)
- Chargement des fichiers CSV depuis GitHub ou une source Blob Storage
- Stockage structuré dans le conteneur **Raw** du Data Lake

### 🔹 Transformation (Databricks)
- Suppression des doublons et valeurs nulles  
- Nettoyage des chaînes de caractères et uniformisation de la casse  
- Normalisation des noms de colonnes (`PersonName` → `athlete_name`, `Country` → `country`, `Discipline` → `sport`)  
- Ajout d’un identifiant unique (`athlete_id`)  
- Création de vues analytiques :  
  - **Athletes by Team** (`Athletes ⨝ Teams`)  
  - **Athletes by Discipline** (`Athletes ⨝ Coaches`)

### 🔹 Stockage & Analyse
- Données transformées sauvegardées dans **Data Lake Gen2 (Silver/Gold layers)**  
- Connexion à **Azure Synapse Analytics** pour modélisation tabulaire
- Exploration et visualisation via **Power BI**

---

## 🧠 Technologies utilisées
| Domaine | Outil / Service |
|----------|----------------|
| ETL & Orchestration | Azure Data Factory |
| Stockage | Azure Data Lake Gen2 |
| Traitement | Azure Databricks (PySpark) |
| Analyse | Azure Synapse Analytics |
| Visualisation | Power BI |
| Langage | Python, SQL |
| Contrôle de version | Git & GitHub |

---

## 📁 Structure du projet
```
📦 olympic-data-pipeline
 ┣ 📂 data/
 ┃ ┣ raw-data/
 ┃ ┣ transformed-data/
 ┃ 
 ┣ 📂 notebooks/
 ┃ ┣ okyo Olympics data transformation.ipynb
 ┃ 
 ┣ 📂 powerbi/
 ┃ ┗ olympic_dashboard.pbix
 ┣ README.md
 ┗ requirements.txt
```

---

## 📊 Résultats attendus
- Données uniformisées et prêtes pour l’analyse  
- Jeux de données interconnectés (Athletes ↔ Teams ↔ Medals)  
- Tableaux de bord Power BI :  
  - Répartition des athlètes par pays et discipline  
  - Nombre de médailles par sport et par pays  
  - Répartition hommes / femmes par sport  

---

## 👨‍💻 Auteur
**Hamza Benaghmouch**  
🎓 Étudiant en Data Engineering | Passionné par Azure & PySpark  
📧 hamzabeng64@gmail.com  

