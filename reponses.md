## Question 3

Le dossier `.github/workflows` sert à stocker les fichiers de workflow GitHub Actions. GitHub lit ces fichiers YAML pour automatiser des tâches dans le repository, par exemple lancer des tests, vérifier le code ou exécuter des actions lors d'un `push` ou d'une `pull request`.

## Question 8

Dans l'onglet Actions, j'ai constaté que le workflow `Hello World` s'est exécuté automatiquement après le push. Le job `hello` a réussi et l'étape `Hello step` a affiché le message `Hello World from GitHub Actions!`.

## Question 10

Après le push, deux workflows se sont exécutés automatiquement : `Hello World` et `Run Tests`. Cela s'explique par le fait que les deux sont configurés pour se déclencher lors d'un `push`. Le workflow `Run Tests` a installé les dépendances puis exécuté les tests avec `pytest`, et tout s'est terminé avec succès.

## Question 11

Après avoir introduit le bug dans `model.py` puis fait un push, le workflow de tests a échoué. Le test `test_predict_positive` ne passe plus, car la fonction retourne `positif` au lieu de `positive`. GitHub Actions permet donc de détecter automatiquement cette régression.

## Question 12

Après avoir corrigé le bug dans `model.py` et poussé la modification, le workflow de tests a de nouveau réussi. Les tests repassent au vert, ce qui confirme que le problème a bien été corrigé.

## Question 14

Après le push, le workflow de tests a lancé plusieurs exécutions du même job avec différentes versions de Python : 3.8, 3.9 et 3.10. J'ai constaté que GitHub Actions exécute ces jobs automatiquement grâce à la matrice, ce qui permet de vérifier la compatibilité du code sur plusieurs versions.

## Question 16

J'ai ajouté une docstring dans le code puis relancé le workflow de lint. Le workflow a réussi, ce qui montre que le code ne contient pas d'erreurs Python critiques détectées par `flake8`.

## Question 18

Lors de l'ouverture de la Pull Request, le workflow `PR Comment` s'est exécuté automatiquement. Il a ajouté un commentaire par `github-actions[bot]` pour remercier de la PR et indiquer que les tests automatisés allaient être lancés.

## Question 21

Après avoir poussé les modifications, le workflow `Build Status Badge` s'est exécuté sur la branche `main`. Le badge ajouté dans le README s'affiche et reflète l'état du workflow. Quand le workflow réussit, le badge indique que le build est réussi.

## Question 24

Après le push, le workflow `Docker Build` est apparu dans l'onglet Actions. Il a construit l'image Docker puis exécuté le conteneur pour tester le programme. Le workflow a réussi, ce qui montre que l'image est bien construite et que le code fonctionne dans un environnement Docker.

## Question 27

Après le push, le workflow `Evaluate Model` s'est exécuté et a généré un artifact nommé `model-metrics`. En le téléchargeant, j'ai constaté qu'il contient un fichier `metrics.json` avec les métriques simulées du modèle, comme l'accuracy, la precision, le recall et le f1-score.

## Question 30

Après plusieurs push, j'ai constaté que le workflow d'évaluation réussit parfois et échoue parfois. Cela dépend de la valeur aléatoire de l'accuracy générée dans `metrics.py`. Quand l'accuracy est supérieure ou égale à 0.9, le workflow passe, sinon il échoue.

## Question 33

Dans l'onglet Actions, j'ai pu déclencher manuellement le workflow `Manual Workflow`. GitHub m'a demandé de choisir un environnement parmi `dev`, `staging` et `prod`. Une fois lancé, le workflow a affiché l'environnement sélectionné puis a exécuté les tests.

## Question 36

Après avoir créé et poussé le tag, le workflow `Create Release` s'est exécuté automatiquement. Dans l'onglet Releases, j'ai constaté qu'une nouvelle release a été créée avec le tag poussé et le nom correspondant.

## Question 38

Après avoir ajouté des commentaires dans `model.py` et poussé le fichier, le workflow `Documentation` s'est exécuté. L'artifact généré contient un dossier `docs` avec un fichier `model.md`, qui correspond à la documentation produite automatiquement à partir du code et des docstrings du module.

## Question 40

Après avoir ajouté une dépendance puis exécuté le workflow deux fois, j'ai constaté que le deuxième passage est plus rapide. Cela s'explique par l'utilisation du cache des dépendances `pip`, qui évite de retélécharger et réinstaller tous les paquets à chaque exécution.

## Question 42

Dans la visualisation du workflow, j'ai constaté que les jobs `lint` et `test` s'exécutent en parallèle. Le job `build` démarre seulement après la fin des deux, puis `deploy` s'exécute en dernier. Cela montre bien la différence entre exécution parallèle et exécution séquentielle avec `needs`.

## Question 44

Je trouve que cette structure est cohérente pour un projet ML réel, car elle suit une logique progressive : tests, évaluation, packaging, déploiement en développement puis en production. Cela permet de sécuriser le déploiement en vérifiant d'abord la qualité du code, les performances du modèle et le bon fonctionnement du package avant de passer en production.
