# Sauvegarde  

## 🔹 Sauvegarde avec `pg_dump`

``` bash
pg_dump -U <utilisateur> -d <nom_base> -F <format> -f <chemin_fichier> -t <table>
``` 

| Composition de la Commande | Description                                   |
| -------------------------- | --------------------------------------------- |
| `-U`                       | Spécifie l’utilisateur PostgreSQL             |
| `-d`                       | Nom de la base de données à sauvegarder       |
| `-F`                       | Format : `p` (texte), `c` (custom), `t` (tar) |
| `-f`                       | Nom du fichier de sortie                      |
| `-t`                       | Pour sauvegarder une **table spécifique**     |

### Formats disponibles

| Format (`-F`)   | Type de fichier généré    | Extension             | Peut contenir...                 | Compatible avec |
| --------------- | ------------------------- | --------------------- | -------------------------------- | --------------- |
| `p` (plain)     | Fichier texte SQL         | `.sql`                | Requêtes SQL (CREATE, INSERT...) | `psql`          |
| `c` (custom)    | Fichier binaire compressé | `.backup` ou `.dump`  | Sauvegarde complète ou partielle | `pg_restore`    |
| `t` (tar)       | Archive tar PostgreSQL    | `.tar`                | Structure + données              | `pg_restore`    |
| `d` (directory) | Dossier avec fichiers     | Dossier (pas fichier) | Une table par fichier            | `pg_restore`    |



### Sauvegarde complète et partielle
*Une sauvegarde complète enregistre toute la base de données (tables, vues..), tandis qu'une sauvegarde partielle te permet de ne sauvegarder qu'une ou plusieurs tables spécifiques.*
| Type                 | Commande                                                                 |
| -------------------- | ------------------------------------------------------------------------ |
| Sauvegarde complète  | `pg_dump -U yousra -d bibliotheque -F c -f backup_complet.dump`          |
| Sauvegarde partielle | `pg_dump -U yousra -d bibliotheque -t utilisateurbib -F c -f table.dump` |

---

## 🔹 Restauration d'une base de données

### Utilisation de `psql` ou `pg_restore`

| Format de sauvegarde | Commande de restauration                                    |
| -------------------- | ----------------------------------------------------------- |
| `.sql` (texte)       | `psql -U yousra -d bibliotheque -f sauvegarde.sql`          |
| `.dump` (custom)     | `pg_restore -U yousra -d bibliotheque -F c sauvegarde.dump` |


## 🔹 Planification des sauvegardes

### Exécution **automatique quotidienne** à 3h du matin

```bash
0 3 * * * pg_dump -U <utilisateur> -d <base_de_donnee> -F c -f /chemin/backup_$(date +\%Y-\%m-\%d).dump
```
# Restauration
## Restauration avec pg_restore
``` bash
pg_restore -U <nom_utilisateur> -d nom_base  <fichier>.backup
``` 
## Restauration avec pg_restore
``` bash
psql -U <nom_utilisateur> -d nom_base -f <fichier>.sql
``` 

### Option supplémentaire 

| **Option**         | **Description**                                        |
|--------------------|--------------------------------------------------------|
| `-f fichier`       | Spécifie le fichier à restaurer (SQL ou backup).       |
| `-v`                | Mode verbeux (affiche les étapes de la restauration).  |
| `--clean`           | Supprime les objets existants avant la restauration.   |
| `--create`          | Crée la base de données avant de restaurer.            |
| `-C`                | Crée la base de données (effet similaire à `--create`).|
| `--no-owner`        | Ne pas restaurer les propriétaires des objets.         |
| `--data-only`       | Restaure seulement les données (sans les structures). |
| `--schema-only`     | Restaure seulement les structures (sans les données). |
