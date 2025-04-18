# Data Control Language (DCL) avec PostgreSQL

##  Gestion des utilisateurs

### 🔹 Création d'utilisateurs
 **Crée un utilisateur sans mot de passe.**
``` bash
CREATE USER nom_utilisateur;
```
 
**Crée un utilisateur avec un mot de passe.**

``` bash
CREATE USER nom_utilisateur WITH PASSWORD 'mot_de_passe';
```

### 🔹 Modification d'utilisateurs
- **ALTER USER nom_utilisateur WITH PASSWORD 'nouveau_mdp';**
  > Change le mot de passe d’un utilisateur existant.

- **ALTER USER nom_utilisateur RENAME TO nouveau_nom;**
  > Renomme un utilisateur.

### 🔹 Suppression d'utilisateurs
- **DROP USER nom_utilisateur;**
  > Supprime un utilisateur, en assurant que  l'utilisateur n'a plus d'objets ou privilèges avant de le supprimer.

---

##  Gestion des droits

La commande `GRANT` permet de donner à un utilisateur des droits spécifiques (*privilèges*) sur une table, une base ou un autre objet PostgreSQL.

### Privilèges disponibles dans PostgreSQL

| Privilège    | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| SELECT       | Lire les données d’une table                                                |
| INSERT       | Ajouter de nouvelles lignes dans une table                                  |
| UPDATE       | Modifier des données existantes dans une table                              |
| DELETE       | Supprimer des lignes d’une table                                             |
| TRUNCATE     | Vider complètement une table rapidement                                      |
| REFERENCES   | Permet de créer une clé étrangère qui pointe vers cette table               |
| USAGE        | Accès à des objets comme des schémas ou des séquences                       |
| EXECUTE      | Exécuter une fonction ou une procédure stockée                              |
| ALL          | Donner tous les privilèges possibles sur l’objet spécifié                   |

### 🔹 Attribution des droits
- **GRANT privilège ON table TO utilisateur;**
  > Ex : `GRANT SELECT, INSERT ON clients TO yousra;`

- **GRANT ALL PRIVILEGES ON DATABASE nom_db TO utilisateur;**
  > Donne tous les droits sur la base.

### 🔹 Révocation des droits
- **REVOKE privilège ON table FROM utilisateur;**
  > Enlève des droits spécifiques.

- **REVOKE ALL PRIVILEGES ON DATABASE nom_db FROM utilisateur;**
  > Retire tous les droits d'accès à la base.

📌 *Impact : L'utilisateur perd l'accès ou la capacité d'interagir avec les objets concernés.*

---

## ✅ Bonnes pratiques de sécurité

- **Principe du moindre privilège** : Ne donner que les droits nécessaires, rien de plus.
- **Gestion des mots de passe** : Utiliser des mots de passe complexes, changer régulièrement.
- **Documentation** : Garder une trace des utilisateurs et des droits accordés.

---

## 🧪 Exercices pratiques

1. Créer un utilisateur `app_user` avec mot de passe :
   ```sql
   CREATE USER app_user WITH PASSWORD 'S3cur3P@ss';
