# SQL - Data Definition Language (DDL) avec PostgreSQL

_Le DDL sert à créer, modifier et supprimer des structures (bases, tables, colonnes, contraintes…)._

---

## Création et gestion des bases de données

| Commande               | Description                            |
| ---------------------- | -------------------------------------- |
| `CREATE DATABASE nom;` | Crée une nouvelle base de données      |
| `DROP DATABASE nom;`   | Supprime une base de données existante |

**Bonnes pratiques** : Des noms clairs, en minuscules, sans espaces, séparés par `_` si besoin.

---

## Création et modification de tables

### Types de données de base

| Type       | Utilisation                            |
| ---------- | -------------------------------------- |
| `INTEGER`    | Nombres entiers                        |
| **DECIMAL**    | Nombres décimaux avec précision        |
| `VARCHAR(n)` | Chaîne de caractères avec longueur max |
| **TEXT**      | Texte sans limite de taille précise    |
| `DATE`       | Date simple (AAAA-MM-JJ)               |
| **TIMESTAMP**  | Date + heure                           |
| `BOOLEAN`    | Vrai ou faux (`TRUE`, `FALSE`)         |

### Structure des tables

| Commande                                       | Description                   |
| ---------------------------------------------- | ----------------------------- |
| `CREATE TABLE nom (...); `                       | Crée une nouvelle table       |
| **ALTER TABLE nom ADD colonne type;**            | Ajoute une colonne            |
| `ALTER TABLE nom ALTER COLUMN col TYPE newtype;` | Modifie le type d’une colonne |
| **ALTER TABLE nom DROP COLUMN colonne;**        | Supprime une colonne          |
| `DROP TABLE nom; `                               | Supprime une table            |

---

## Gestion des contraintes

| Contrainte        | Utilité                                                |
| ----------------- | ------------------------------------------------------ |
| **PRIMARY KEY**       | Identifie chaque ligne de façon unique                 |
|`FOREIGN KEY `      | Lien avec une clé primaire d’une autre table           |
| **NOT NULL**          | Empêche les valeurs vides                              |
| `UNIQUE `           | Empêche les doublons dans une colonne                  |
| **DEFAULT valeur**    | Valeur insérée automatiquement si aucune n’est fournie |
|`CHECK (condition)` | Vérifie qu’une valeur respecte une règle               |

---

## Index

| Élément                             | Description                                                |
| ----------------------------------- | ---------------------------------------------------------- |
| `CREATE INDEX nom ON table(colonne);` | Crée un index simple pour accélérer les recherches         |
| À utiliser quand                    | Sur colonnes très utilisées dans WHERE, JOIN, ORDER BY…    |

---
