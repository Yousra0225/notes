# 🐘 Cheatsheet PostgreSQL (psql & pgcli)

## Connexion à PostgreSQL

### Avec `psql` :
```bash
psql -U <utilisateur> -d <base_de_donnee>
```

### Avec `pgcli` :
```bash
pgcli -U <utilisateur> -d <base_de_donnee>
```

---

## Gestion des mots de passe

Changer le mot de passe d’un utilisateur :
```sql
ALTER USER nom_utilisateur WITH PASSWORD 'nouveau_mot_de_passe';
```

---

##  Création d’une base de données

Créer une base simple :
```bash
createdb nom_de_la_base -U utilisateur
```

Créer avec encodage et collation :  
  **--encoding=UTF8**: *spécifie le jeu de caractères utilisé pour stocker les textes.*
  - UTF8 = encodage universel (supporte tous les caractères, emojis, langues…).  

  **--lc-collate** : *Définit comment trier les données textuelles (ordre alphabétique).*
  - fr_FR.UTF-8 = tri selon les règles françaises (ex : é après e).

```bash
createdb nom_de_la_base \
  --encoding=UTF8 \ 
  --lc-collate=fr_FR.UTF-8 \
  --lc-ctype=fr_FR.UTF-8 \
  -U utilisateur
```

Vérifier les bases existantes :
```bash
psql -U utilisateur -l
```

---

##  Connexion à une base de données

```bash
psql -U <utiliateur> -d  <base_de_donnee>
```
ou
```bash
pgcli -U <utiliateur> -d  <base_de_donnee>
```

---

##  Création d’un schéma (optionnel)

```sql
CREATE SCHEMA mon_schema;
```


---

##  Requêtes simples

Afficher tout :
```sql
SELECT * FROM utilisateurs;
```

Filtrer :
```sql
SELECT * FROM utilisateurs WHERE age > 24;
```

---

## Vérification de l'encodage et collation

Lister les bases avec détails :
```bash
psql -l
```

---

## Commandes utiles dans `psql`/`pgcli`

| Commande          | Description                                                   |
|-------------------|---------------------------------------------------------------|
| `\l`              | Lister toutes les bases de données                            |
| `\c nom_base`     | Se connecter à une base de données                            |
| `\dt`             | Lister les tables dans la base courante                       |
| `\d nom_table`    | Afficher la structure (schéma) d'une table                    |
| `\dn`             | Lister les schémas                                            |
| `\df`             | Lister les fonctions définies                                 |
| `\du`             | Lister les rôles (utilisateurs)                               |
| `\conninfo`       | Voir les infos de connexion actuelles                         |
| `\q`              | Quitter `psql` ou `pgcli`                                     |

```
---
