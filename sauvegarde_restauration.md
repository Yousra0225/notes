# Sauvegarde et restauration PostgreSQL

## 🔹 Sauvegarde avec `pg_dump`

### Formats disponibles

| Option | Description                                   |
| ------ | --------------------------------------------- |
| `-U`   | Spécifie l’utilisateur PostgreSQL             |
| `-d`   | Nom de la base de données à sauvegarder       |
| `-F`   | Format : `p` (texte), `c` (custom), `t` (tar) |
| `-f`   | Nom du fichier de sortie                      |
| `-t`   | Pour sauvegarder une **table spécifique**     |

---

### Sauvegarde complète et partielle

| Type                 | Commande                                                                 |
| -------------------- | ------------------------------------------------------------------------ |
| Sauvegarde complète  | `pg_dump -U yousra -d bibliotheque -F c -f backup_complet.dump`          |
| Sauvegarde partielle | `pg_dump -U yousra -d bibliotheque -t utilisateurbib -F c -f table.dump` |

---

## 🔹 Restauration d'une base de données

### [X] Utilisation de `psql` ou `pg_restore`

| Format de sauvegarde | Commande de restauration                                    |
| -------------------- | ----------------------------------------------------------- |
| `.sql` (texte)       | `psql -U yousra -d bibliotheque -f sauvegarde.sql`          |
| `.dump` (custom)     | `pg_restore -U yousra -d bibliotheque -F c sauvegarde.dump` |

---


## 🔹 Planification des sauvegardes 

### Exécution **automatique quotidienne** à 3h du matin

```bash
0 3 * * * pg_dump -U <utilisateur> -d <base_de_donnee> -F c -f /chemin/backup_$(date +\%Y-\%m-\%d).dump
```
