# Biblio :book:

Logiciel de gestion de bibliothèque.

## Sommaire

- [Prérequis](#prérequis)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Tests](#tests)
- [Structure du projet](#structure-du-projet)
- [Contribuer](#contribuer)
- [Auteurs](#auteurs)

## Prérequis

- [Python3](https://python.org/) (développé sous Python v3.14.7)
- [Git](https://git-scm.org/)

## Installation

1. Cloner le dépôt soit avec GitHub Desktop soit avec Git CLI

```sh
git clone https://github.com/GADEL-01/biblio-tp
```

2. Ouvrir le dossier du repository dans une invite de commande/terminal.

3. Créer la base de démonstration (à faire une fois, avant le reste)

```sh
python biblio.py init
```

Résultat attendu :

```sh
Base initialisee : 6 livres, 3 membres.
```

Sous macOS ou Linux : python3. Sous Windows, si python ne marche pas : py.

## Utilisation

Toutes les commandes se lancent depuis la racine du dépôt, après avoir fait `python biblio.py init` (voir Installation). Sous macOS ou Linux : `python3`. Sous Windows, si `python` ne marche pas : `py`.

### Lister les livres

```sh
python biblio.py livres
```

Résultat attendu :

```txt
[1] L'Etranger (Albert Camus) : disponible
[2] Dune (Frank Herbert) : emprunte
[3] Le Petit Prince (Antoine de Saint-Exupery) : disponible
[4] Fondation (Isaac Asimov) : disponible
[5] Les Miserables (Victor Hugo) : disponible
[6] Neuromancien (William Gibson) : disponible
```

### Chercher un livre

```sh
python biblio.py chercher "Dune"
```

Résultat attendu :

```sh
[2] Dune (Frank Herbert)
```

### Emprunter un livre

```sh
python biblio.py emprunter <id_livre> <id_membre>
```

Exemple :

```sh
python biblio.py emprunter 3 1
```

Résultat attendu :

```sh
Emprunt enregistre : livre 3, membre 1.
```

### Rendre un livre

```sh
python biblio.py rendre <id_livre>
```

Exemple :

```sh
python biblio.py rendre 3
```

Résultat attendu :

```sh
Retour enregistre pour le livre 3.
```

### Lister les retards

```sh
python biblio.py retards
```

Résultat attendu (liste les livres empruntés depuis plus de 14 jours et non rendus) :

```sh
Dune, emprunte par Alice Martin : 254 jours de retard
```

## Tests

```
python -m unittest discover -s tests -t .
```

Résultat attendu :

```
Ran 4 tests in 0.1s

OK
```

Sous macOS ou Linux : `python3`. Sous Windows, si `python` ne marche pas : `py`.

## Structure du projet

```
biblio-tp/
├── biblio.py               # programme principal
├── README.md               # ce fichier
├── CONTRIBUTING.md         # règles de contribution
├── docs/
│   ├── adr/                # décisions techniques (ADR)
│   └── circulation.md
├── tests/
│   └── test_biblio.py      # tests automatisés
└── .github/
    ├── ISSUE_TEMPLATE/     # modèles d'issues
    └── workflows/          # intégration continue
```

## Contribuer

Merci de vous référer au fichier [CONTRIBUTING.md](./CONTRIBUTING.md)

## Auteurs

### **🫪 Chokbar Team 🫪**

🫪 M4elstr0m & GADEL-01 🫪
