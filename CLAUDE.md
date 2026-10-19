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

**Au QG aussi, seul l'orchestrateur pousse sur `main`.** Un autre rôle qui y écrit — sa clôture, sa capitalisation —
pousse une branche courte (`capitalisation/<rôle>-<AAAAMMJJ-HHMM>`), que l'orchestrateur relit et fusionne : c'est
la PR de `/koa:clore`, sans forge à PR. À la recette du 19/10/2026, deux clôtures parallèles ont fait l'une un push
direct sur `main`, l'autre une branche.

## Environnements

Rien ne se déploie depuis ce cluster. Les distros de l'équipe sont des Debian minimales : `python3` (pas de
`python`), `pytest`, `venv`, `make`, `git` ; ni `docker`, ni `gh`. Un fait d'environnement appris en chantier
s'écrit **ici**, une fois pour l'équipe — pas dans la page de chaque rôle.

## Interdits

- Jamais de push forcé ; jamais de réécriture de `main`.
- Aucun secret, nulle part : il n'y en a aucun à manier ici.
- Rien hors de `~/projet`, de `$KOA_QG` et de son propre dépôt de seed.

## Mémoire

- Les lois et consignes : [`docs/KB/REGLES/`](docs/KB/REGLES/README.md) — contraignantes.
- Les plans d'itération : [`docs/missions/`](docs/missions/README.md), un fichier par itération.
- Ce que chaque rôle apprend ici : `docs/KB/equipe/<rôle>.md`.
