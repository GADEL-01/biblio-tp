# ADR 0002 : SQLite plutôt qu'un fichier JSON ou un serveur PostgreSQL

- Statut : proposé
- Date : 2026-10-05
- Décideurs : M4elstr0m

## Contexte

Biblio est utilisé par une petite bibliothèque associative. Les bénévoles installent et font tourner le logiciel eux-mêmes, sur leurs propres postes, sans compétences système. Il faut stocker les livres, les membres et les prêts de façon fiable (pas de prêt perdu, pas de doublon), avec des requêtes simples (recherche, retards), sans demander aux bénévoles d'installer et d'administrer un serveur de base de données.

## Options envisagées

1. Un fichier JSON lu et réécrit en entier à chaque commande.
2. Un serveur PostgreSQL auquel le script se connecte.
3. SQLite, un fichier de base de données unique, sans serveur séparé.

## Décision

Biblio stocke ses données dans un fichier SQLite plutôt que dans un fichier JSON ou sur un serveur PostgreSQL.

## Conséquences

Plus facile :
- Aucune installation de serveur : `python biblio.py init` suffit, le module `sqlite3` est inclus dans la bibliothèque standard Python.
- Sauvegarder ou transmettre la base revient à copier un seul fichier `.db`.
- De vraies requêtes SQL avec transactions et contraintes (clés étrangères), contrairement à un fichier JSON qu'il faudrait entièrement recharger et valider à la main.

Plus difficile :
- Pas d'accès concurrent propre si plusieurs bénévoles veulent utiliser Biblio en même temps depuis des postes différents sur le même fichier.
- Si l'association grandit (plusieurs antennes, besoin d'un accès partagé à distance), il faudra migrer vers une solution avec un vrai serveur comme PostgreSQL.
