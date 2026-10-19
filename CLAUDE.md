# QG du cluster « banc »

Ce cluster est un **banc de recette** de KoA : une petite équipe d'agents y mène un micro-chantier, pour qu'on
mesure comment elle travaille. Il suit le framework agentique KoA (`library://koa/architecture`) et la méthode
de la table (`library://equipe/table`), qui **font foi**.

## Carte

| Dépôt | Rôle | Adresse de travail |
|---|---|---|
| `qg` | ce dépôt : lois, consignes, plans d'itération, mémoire d'équipe | `git://127.0.0.1/qg.git` |
| `projet` | le code du chantier | `git://127.0.0.1/projet.git` |

Les deux se servent par une **forge locale** (`git daemon`), sans authentification, joignable de toutes les
distros de l'équipe. Le QG est cloné dans `$KOA_QG`, le projet dans `~/projet`. Il n'y a ni GitHub, ni PR :
une branche par mission, une tête se désigne par son SHA complet, une revue se fait sur
`git diff <base>...<sha>`, et l'orchestrateur fusionne sur `main` par `git merge --ff-only` ou `--no-ff`.

## Environnements

Aucun. Rien ne se déploie depuis ce cluster.

## Interdits

- Jamais de push forcé ; jamais de réécriture de `main`.
- Aucun secret, nulle part : il n'y en a aucun à manier ici.
- Rien hors de `~/projet`, de `$KOA_QG` et de son propre dépôt de seed.

## Mémoire

- Les lois et consignes : [`docs/KB/REGLES/`](docs/KB/REGLES/README.md) — contraignantes.
- Les plans d'itération : [`docs/missions/`](docs/missions/README.md), un fichier par itération.
- Ce que chaque rôle apprend ici : `docs/KB/equipe/<rôle>.md`.
