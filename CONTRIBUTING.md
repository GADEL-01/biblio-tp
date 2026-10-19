# Contribuer à Biblio

## Avant de coder

- Chercher si une issue existe déjà pour le sujet avant d'en ouvrir une nouvelle.
- Ouvrir une issue avec le bon modèle : **Signaler un bug**, **Proposer une évolution** ou **Poser une question**.
- Pour un blocage en cours de travail (PR qui n'avance pas, conflit, dépendance sur quelqu'un), utiliser le modèle **Signaler un blocage**.
- Ne jamais commencer une branche sans issue : son numéro sert à nommer la branche et à fermer l'issue depuis la PR.

## Branches

Convention définie par l'[ADR 0004](docs/adr/0004-convention-de-branches.md) : `type/n°-mots-cles`, où `type` est `fix`, `feat` ou `docs` selon la nature du changement.

- `fix/3-double-emprunt`
- `feat/5-afficher-emprunteur`
- `docs/12-readme`

Toujours créer la branche depuis `main` à jour (`Pull origin` avant `New branch`).

## Commits

Format `type: message`, au présent, décrivant ce que fait le commit :

- `fix: refuse un emprunt déjà en cours`
- `feat: afficher l'emprunteur dans la liste des livres`
- `docs: ADR 0004 convention de branches`

Un commit traite un seul sujet. Pas de commit `wip` ou `fix typo` laissé tel quel dans l'historique final.

## Pull requests

- Une branche = une issue = une PR.
- La description suit le modèle du dépôt (Contexte, Changements, Impact, Comment tester) et contient `Closes #n`.
- `main` est protégée : impossible de merger sans PR, sans approbation et sans que les tests passent.

## Review

- Le relecteur n'est jamais l'auteur de la PR (`CODEOWNERS` impose au moins deux personnes par zone du dépôt).
- Avant d'approuver : les tests passent (CI verte), la PR traite un seul sujet, le code suit les règles déjà actées (ex. [ADR 0003](docs/adr/0003-requetes-parametrees.md) sur les requêtes paramétrées).
- Refuser (**Request changes**) si : les tests sont rouges, la PR mélange plusieurs sujets, ou le comportement décrit dans l'issue n'est pas respecté. Expliquer pourquoi en commentaire, pas juste refuser sans justification.
- Une fois approuvée, l'auteur de la PR merge et supprime la branche.

## Definition of Done

Une tâche est terminée quand :

- [ ] Le code répond au besoin décrit dans l'issue
- [ ] `python -m unittest` passe en local et dans la CI
- [ ] La PR a été relue et approuvée par quelqu'un d'autre que l'auteur
- [ ] La documentation concernée (README, ADR, CONTRIBUTING) est à jour si le comportement a changé
- [ ] La PR est mergée dans `main` et la branche supprimée
- [ ] L'issue correspondante est fermée automatiquement (`Closes #n`) ou manuellement si besoin

## Signaler un blocage

Si une PR n'avance pas (pas de review, conflit non résolu, dépendance sur un autre membre) ou si une échéance est en jeu :

1. Ouvrir une issue avec le modèle **Signaler un blocage**.
2. Remplir les cinq champs : tâche concernée, blocage exact (erreur copiée, pas résumée), ce qui a déjà été essayé, ce dont on a besoin (en mentionnant la personne avec `@pseudo`), échéance.
3. La personne mentionnée répond en commentaire avec une action concrète (qui fait quoi, quand).
4. L'auteur ferme l'issue une fois débloqué.
