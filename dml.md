# ✏️ SQL - Data Manipulation Language (DML) avec PostgreSQL

> Le DML sert à interroger et modifier les données dans les tables.

---

## Requêtes de sélection (SELECT)

### Structure de base

| Élément               | Utilité                                 |
| --------------------- | --------------------------------------- |
| ` SELECT colonne`     | Sélectionne les colonnes à afficher     |
| FROM table            | Précise la table source                 |
| `WHERE condition`     | Filtre les lignes selon une condition   |
| ORDER BY col ASC/DESC | Trie les résultats                      |
| `LIMIT n  `           | Limite le nombre de résultats           |
| GROUP BY col          | Regroupe les lignes par une colonne     |
| `HAVING condition`    | Filtre sur les groupes (après GROUP BY) |

### Opérateurs de comparaison

| Opérateur         | Signification                |
| ----------------- | ---------------------------- |
| =                 | Égal à                       |
| `<>`              | Différent de                 |
| >, <, >=, <=      | Supérieur / inférieur        |
| `BETWEEN a AND b` | Entre a et b                 |
| IN (a, b, c)      | Appartient à la liste        |
| `LIKE 'mot%'`     | Correspondance avec un motif |
| IS NULL           | Valeur manquante             |
| `IS NOT NULL`     | Valeur présente              |

### Fonctions d’agrégation

| Fonction  | Description                |
| --------- | -------------------------- |
| `COUNT()` | Compte le nombre de lignes |
| **SUM()** | Additionne les valeurs     |
| ` AVG()`  | Moyenne                    |
| **MIN()** | Valeur minimale            |
| `MAX()`   | Valeur maximale            |

---

## Jointures de tables

| Type de jointure | Description                                   |
| ---------------- | --------------------------------------------- |
| `INNER JOIN `    | Lignes communes aux deux tables               |
| **LEFT JOIN**    | Toutes les lignes de gauche + correspondances |
| `RIGHT JOIN `    | Toutes les lignes de droite + correspondances |

**Bonnes pratiques** : toujours préciser les alias (`t1.col`, `t2.col`) pour éviter les ambiguïtés.

---

## Insertion de données

| Commande                                          | Description                                   |
| ------------------------------------------------- | --------------------------------------------- |
| `INSERT INTO table (col1, col2) VALUES (v1, v2);` | Insertion simple                              |
| **INSERT INTO table VALUES (v1), (v2), (v3);**    | Insertion multiple                            |
| `INSERT INTO table SELECT ...; `                  | Insertion à partir d’une autre requête SELECT |

---

## Modification de données

| Commande                                      | Description                          |
| --------------------------------------------- | ------------------------------------ |
| `UPDATE table SET col = val WHERE condition;` | Met à jour une ou plusieurs colonnes |
| **UPDATE ... FROM ... WHERE ...;**            | Mise à jour avec jointure            |

---

## Suppression de données

| Commande                        | Description                                   |
| ------------------------------- | --------------------------------------------- |
| `DELETE FROM table WHERE ...; ` | Supprime les lignes répondant à une condition |
| **TRUNCATE TABLE nom;**         | Vide complètement une table (sans WHERE)      |

**TRUNCATE** est plus rapide que `DELETE`, mais irréversible et sans déclencheurs.

---
