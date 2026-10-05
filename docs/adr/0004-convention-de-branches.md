# ADR 0004 : Convention de nommage des branches

- Statut : proposé
- Date : 2026-10-05
- Décideurs : GADEL-01, M4elstr0m

## Contexte

Plusieurs branches coexistent dans le dépôt. Sans règle commune, il est difficile de comprendre à quoi correspond une branche en lisant son nom, et de la relier à l'issue correspondante. L'équipe a besoin de retrouver rapidement quelle branche corrige quel bug ou ajoute quelle fonctionnalité.

## Options envisagées

1. **Nom libre** : chaque membre nomme sa branche comme il le souhaite (ex. `correction`, `test-nadia`, `wip`).
   - Pour : aucune contrainte, rapide à créer.
   - Contre : impossible de relier une branche à une issue ou à un type de changement ; la liste des branches devient illisible.

2. **Convention `type/n°-mots-cles`** : le nom encode le type de changement, le numéro d'issue et un court résumé (ex. `fix/3-double-emprunt`, `docs/12-readme`).
   - Pour : lien direct avec l'issue, type visible au premier coup d'œil, tri naturel par type.
   - Contre : légèrement plus long à taper ; demande de connaître le numéro d'issue avant de créer la branche.

## Décision

Les branches suivent le format `type/n°-mots-cles`, où `type` est `fix`, `feat` ou `docs` selon la nature du changement.

## Conséquences

Plus facile : retrouver l'issue liée à une branche, comprendre la liste des branches en un coup d'œil, rédiger le message de commit et la description de PR.

Plus difficile : il faut ouvrir l'issue avant de créer la branche pour en connaître le numéro.
