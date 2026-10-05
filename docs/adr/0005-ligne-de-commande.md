# ADR 0005 : Interface en ligne de commande plutôt qu'un site web

- Statut : accepté
- Date : 2026-10-05
- Décideurs : GADEL-01, M4elstr0m

## Contexte

Biblio est utilisé par des bénévoles d'une association pour gérer les prêts de livres. Il fallait choisir comment ces bénévoles interagissent avec le logiciel : via un terminal (CLI) ou via un navigateur web (interface web). Ce choix impacte l'installation, la maintenance et l'accessibilité du logiciel.

## Options envisagées

1. **Interface en ligne de commande (CLI)** : le programme se lance dans un terminal avec des commandes comme `python biblio.py livres`.
   - Pour : aucune dépendance externe, fonctionne partout où Python est installé, simple à déployer.
   - Contre : moins accessible pour des utilisateurs non techniques ; pas d'interface visuelle.

2. **Interface web** : un serveur web tourne en local ou sur un serveur distant, les bénévoles accèdent à Biblio via leur navigateur.
   - Pour : plus accessible et intuitive pour des non-techniciens ; interface graphique possible.
   - Contre : nécessite un serveur web (Flask, Django…), des dépendances supplémentaires, une configuration réseau ; plus complexe à installer et maintenir pour une petite association.

## Décision

Biblio utilise une interface en ligne de commande (CLI), sans serveur ni dépendance externe.

## Conséquences

Plus facile : installer et lancer Biblio sur n'importe quelle machine avec Python ; pas de configuration réseau ni de serveur à maintenir.

Plus difficile : les bénévoles peu à l'aise avec le terminal doivent être formés ; pas d'accès multi-utilisateurs simultané depuis plusieurs machines.
