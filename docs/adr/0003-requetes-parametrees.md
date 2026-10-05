# ADR 0003 : requêtes SQL paramétrées obligatoires

- Statut : accepté
- Date : 2026-10-05
- Décideurs : M4elstr0m

## Contexte

`search_books` construisait sa requête SQL par concaténation de chaînes (`"... LIKE '%" + text + "%'"`). Dès que le texte saisi contenait une apostrophe (ex : "L'Etranger"), la requête devenait invalide et le programme plantait. Au-delà du crash, cette façon d'écrire la requête ouvre la porte à une injection SQL : n'importe quel texte saisi est inséré tel quel dans la commande SQL exécutée. Le reste du fichier utilise déjà des paramètres `?` pour ses requêtes ; il faut fixer une règle explicite pour que cette pratique reste la norme et que l'incident ne se reproduise pas ailleurs.

## Options envisagées

1. Nettoyer ou échapper le texte saisi (par exemple doubler les apostrophes) avant de l'insérer dans la requête.
2. Toujours utiliser des requêtes paramétrées (`?`) fournies par `sqlite3`, en séparant la requête des valeurs.

## Décision

Toutes les requêtes SQL de Biblio doivent utiliser des paramètres `?`, jamais de concaténation de chaînes pour insérer une valeur dans une requête.

## Conséquences

Plus facile :
- Plus aucun risque d'injection SQL via les entrées utilisateur, puisque `sqlite3` échappe lui-même les valeurs passées en paramètre.
- Le code est homogène : une seule façon d'écrire une requête avec des valeurs variables, ce qui facilite la relecture et la review.
- Un texte contenant une apostrophe ou tout autre caractère spécial ne fait plus planter le programme.

Plus difficile :
- Écrire une requête avec des valeurs variables demande un peu plus de rigueur (séparer le texte SQL fixe des paramètres) qu'une simple concaténation.
- En review, il faut rester vigilant pour repérer toute nouvelle requête qui reviendrait à construire du SQL par concaténation de chaînes.
