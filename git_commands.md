# Git : Commandes et Utilité

| Commande | Utilité |
|----------|---------|
| `git add` | Ajoute un fichier au staging (zone de préparation) |
| `git commit` | Sauvegarde les changements dans l’historique |
| `git merge` | Fusionne deux branches |
| `git rebase` | Réécrit l’historique en appliquant les commits ailleurs |
| `git reset` | Reculer HEAD (supprime commits si `--hard`) |
| `git revert` | Annuler un commit sans toucher à l’historique |
| `git stash` | Met de côté les changements sans commit |
| `git fetch` | Récupère les changements distants sans les appliquer |
| `git pull` | `fetch` + `merge` (met à jour la branche locale) |
| `git cherry-pick` | Appliquer un commit spécifique sur une autre branche |
| `git bisect` | Trouver le commit responsable d’un bug |

---

## Explications rapides

### `git add`
Prépare les fichiers pour le commit :
```bash
git add <fichier>
```

### `git commit`
Crée un commit avec un message :
```bash
git commit -m "Message du commit"
```

### `git merge`
Fusionne une branche dans la branche actuelle :
```bash
git merge <branche>
```

### `git rebase`
Réapplique les commits d’une branche sur une autre :
```bash
git rebase main
```

### `git reset`
Annule des commits récents :
```bash
git reset --soft HEAD~1  # Annule le dernier commit mais garde les changements
git reset --hard HEAD~1  # Supprime complètement le dernier commit
```

### `git revert`
Annule un commit avec un commit correctif :
```bash
git revert HEAD
```

### `git stash`
Sauvegarde les modifications en attente :
```bash
git stash
git stash pop  # Récupère les modifications
```

### `git fetch`
Récupère les mises à jour distantes sans les appliquer :
```bash
git fetch origin
```

### `git pull`
Récupère et fusionne les mises à jour :
```bash
git pull origin main
```

### `git cherry-pick`
Applique un commit spécifique :
```bash
git cherry-pick <commit-hash>
```

### `git bisect`
Trouve le commit qui a introduit un bug :
```bash
git bisect start
git bisect bad
git bisect good <commit-hash>
```
Puis tester les commits proposés jusqu'à trouver le problème.

---

📌 **Fichier rédigé pour une utilisation rapide des commandes Git !**
