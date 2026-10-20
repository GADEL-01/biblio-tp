# Circulation de l'information : groupe Chokbar Team

## 1. Rôles
Rédigé par : @GADEL-01

Le groupe est composé de deux membres, chacun cumule les rôles. GADEL-01 est propriétaire du dépôt. Chacun ouvre ses issues, écrit ses PR et relit celles de l'autre. Une PR est mergée uniquement après l'approbation de l'autre membre.

## 2. Où circule chaque information
Rédigé par : @M4elstr0m

| Information | Qui la produit | Qui la valide | Où elle est stockée | Durée de vie |
|---|---|---|---|---|
| Code source | L'auteur de la PR | L'autre membre (1 approbation) | Dépôt GitHub, branche main | Permanente |
| Bug signalé | Celui qui le constate | L'autre membre | Issue GitHub (modèle bug) | Jusqu'à la PR avec Closes #n |
| Décision technique | L'auteur de l'ADR | L'autre membre, via la PR | docs/adr/ | Permanente |
| Documentation d'installation | L'auteur de la modification | L'autre membre, via la PR | README.md | Permanente, mise à jour avec le code |
| Question rapide entre membres | Les deux | Personne | Discord | Éphémère |
| Compte rendu de réunion | Celui qui anime | L'autre membre | Dans l'issue ou la PR concernée | Jusqu'à la fermeture |

## 3. Règles de l'équipe
Rédigé par : @GADEL-01

Titres d'issue : "Bug : ...", "Evolution : ...", "Question : ...", "Bloqué : ...". Labels : bug, enhancement, question.
Branches : type/n°-mots-cles (ADR 0004). Commits : fix:, docs:, feat:.
Règle à partir de la séance 2 : aucun push direct sur main, tout passe par une pull request relue. Depuis la séance 4, GitHub l'impose (PR obligatoire, 1 approbation, CODEOWNERS, check tests).
