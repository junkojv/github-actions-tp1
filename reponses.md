## Question 3

Le dossier `.github/workflows` sert à stocker les fichiers de workflow GitHub Actions. GitHub lit ces fichiers YAML pour automatiser des tâches dans le repository, par exemple lancer des tests, vérifier le code ou exécuter des actions lors d'un `push` ou d'une `pull request`.

## Question 8

Dans l'onglet Actions, j'ai constaté que le workflow `Hello World` s'est exécuté automatiquement après le push. Le job `hello` a réussi et l'étape `Hello step` a affiché le message `Hello World from GitHub Actions!`.

## Question 10

Après le push, deux workflows se sont exécutés automatiquement : `Hello World` et `Run Tests`. Cela s'explique par le fait que les deux sont configurés pour se déclencher lors d'un `push`. Le workflow `Run Tests` a installé les dépendances puis exécuté les tests avec `pytest`, et tout s'est terminé avec succès.

## Question 11

Après avoir introduit le bug dans `model.py` puis fait un push, le workflow de tests a échoué. Le test `test_predict_positive` ne passe plus, car la fonction retourne `positif` au lieu de `positive`. GitHub Actions permet donc de détecter automatiquement cette régression.
