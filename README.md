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

## Installation

1. Cloner le dépôt soit avec GitHub Desktop soit avec Git CLI

```sh
git clone https://github.com/GADEL-01/biblio-tp
```

3. Ouvrir le dossier du repository dans une invite de commande/terminal.

4. Créer la base de démonstration (à faire une fois, avant le reste)

```sh
python biblio.py init
```

Résultat attendu :

```sh
Base initialisee : 6 livres, 3 membres.
```

Sous macOS ou Linux : python3. Sous Windows, si python ne marche pas : py.

## Utilisation

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
