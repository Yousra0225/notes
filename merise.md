
# Cheatsheet Merise

## Introduction
Merise est une méthode d’analyse, de conception et de gestion de projet pour les systèmes d'information, qui permet de modéliser séparément les données et les traitements.

---

## 1. **Concepts Clés de Merise**

### 1.1 **Entité**
Une **entité** est un objet d'intérêt pour l'entreprise, représentant un concept clé.  
Exemples : Client, Commande, Produit.

### 1.2 **Association**
Les **associations** définissent les relations entre les entités.  
Exemple : Un **client** passe une **commande**.

### 1.3 **Identifiant**
L'**identifiant** est une propriété unique qui permet d'identifier une entité de façon distincte.  
Exemple : Le **code client** pour identifier un client.

---

## 2. **Les Niveaux de Merise**

### 2.1 **Modèle Conceptuel des Données (MCD)**  
Le MCD représente les données sous forme d’entités et d’associations.  
- **But** : Modéliser les données de manière abstraite, sans se soucier de la technique.
- **Exemple** : Entités Client, Commande, Produit, avec des associations entre elles.

### 2.2 **Modèle Logique des Données (MLD)**
Le MLD est la traduction du MCD en un modèle plus détaillé, prêt à être implémenté dans une base de données relationnelle.


| **Modèle**                  | **Description**                                                                                                                                  | **But**                                                           | **Exemples**                                                                 |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|-----------------------------------------------------------------------------|
| **Modèle Conceptuel des Données (MCD)** | Le MCD représente les entités, leurs attributs et les relations entre elles de manière abstraite, sans se soucier de l’implémentation.     | Modéliser les données de façon abstraite pour comprendre la structure du système d’information. | - Entité : **Client** (id_client, nom, adresse) <br> - Relation : Un **Client** peut passer plusieurs **Commandes**. |
| **Modèle Logique des Données (MLD)**    | Le MLD transforme le MCD en un modèle adapté aux bases de données relationnelles. Il définit les tables, les clés primaires et étrangères.    | Traduire le MCD pour le rendre prêt à être implémenté dans une base de données relationnelle.       | - Tables : **Client**(id_client, nom, adresse), **Commande**(id_commande, id_client, date) <br> - Clé étrangère : id_client dans la table Commande. |
| **Modèle Physique des Données (MPD)**   | Le MPD décrit l’implémentation physique des données dans le SGBD. Il prend en compte les contraintes de performance et les spécificités du système. | Optimiser la gestion des données pour le SGBD, en définissant les index, partitions, et types de données. | - Index sur **id_client** pour accélérer les recherches. <br> - Partitionnement des tables en fonction des dates de commande. |
