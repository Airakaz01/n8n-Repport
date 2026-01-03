# 🌦️ ETL Avancé avec n8n : Surveillance Météo & Qualité de l'Air

Ce dépôt contient le rendu de l'exercice avancé de workflow automation (ETL) réalisé avec **n8n**. Le projet consiste en un système automatisé de surveillance opérationnelle pour une entreprise de logistique présente dans 5 grandes villes européennes.

## 📄 Rapport Complet
> **Consultez le rapport détaillé et interactif ici :**  
> [**Rapport d'Exercice - EL HOUARI Zakaria**](https://narrow-buckaroo-a17.notion.site/Rapport-d-Exercice-ETL-Avanc-avec-n8n-2dda55f1b33a80cc8d43d81906e97c7a?source=copy_link)

---

## 🚀 Objectifs du Projet
1. **Extraction (Extract)** : Récupération automatisée des données météo et de qualité de l'air via les APIs Open-Meteo.
2. **Transformation (Transform)** : 
   - Calcul d'un score de risque composite (Température, Vent, Précipitations, AQI).
   - Gestion des itérations ville par ville (Looping).
   - Routage conditionnel des alertes.
3. **Chargement (Load)** : 
   - Agrégation des données pour générer des rapports consolidés (HTML, CSV, JSON).
   - Envoi de notifications Webhook pour les alertes critiques (Score > 80).

## 🛠️ Architecture du Workflow
Le workflow se compose de **14 nœuds** organisés selon une logique de traitement itératif :
- **Initialisation** : Liste des villes et coordonnées GPS.
- **Boucle de traitement** : Split in Batches → Appels API → Merge → Calcul JS (Code Node) → IF Condition.
- **Agrégation** : Collecte de tous les résultats après la boucle pour la génération des fichiers finaux.

## 📦 Contenu du dépôt
- `README.md` : Présentation du projet.
- `Exercice_Meteo_Final.json` : Le fichier exporté du workflow n8n (prêt à être importé).
- *(Optionnel)* : Tu peux ajouter ici une capture d'écran de ton workflow.

## 🔧 Installation
Pour tester le workflow :
1. Installez n8n (via Docker ou npm).
2. Créez un nouveau workflow.
3. Importez le fichier `Exercice_Meteo_Final.json`.
4. Configurez l'URL de votre propre webhook dans le nœud `Webhook_Alert` (ex: via Webhook.site).
5. Cliquez sur **Test Workflow**.

---
**Étudiant :** EL HOUARI Zakaria  
**Date :** 3 janvier 2026
