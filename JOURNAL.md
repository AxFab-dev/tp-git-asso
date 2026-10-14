# Journal

## 2026-10-14 — Fusion de `feature/projets` dans `main`

Les fichiers de la branche ont été relus avant la fusion : `.gitignore`,
`main/index.html` et `projets.html`.

Aucun conflit n'est apparu, car `main` n'a pas reçu de modification concurrente
depuis la création de `feature/projets`. La branche ajoute `.gitignore` et
`projets.html`, et sa seule modification d'une ligne existante dans
`main/index.html` ne chevauche aucun changement fait sur `main`.

## 2026-10-14 — Conflit de rebase sur le pied de page

A avait créé `feature/footer` depuis `main`, avec « depuis 2026 » dans le
pied de page. Pendant ce temps, B a fusionné `feature/mentions` dans `main`,
avec « mentions légales » sur cette même ligne.

Lors du rebase de `feature/footer` sur le `main` mis à jour, Git a d'abord
placé `HEAD` sur le nouveau `main`, qui contient la version de B. Le commit
de A est le changement rejoué par le rebase (`REBASE_HEAD`). Ainsi, dans ces
marqueurs, `HEAD` montre la version de B et la section après `=======` celle
de A, contrairement à l'intuition qu'on peut avoir d'un merge classique :
un rebase repart de la nouvelle base puis rejoue les commits de la branche.

Le conflit a été résolu en combinant les deux informations :
`<footer>Association Les Codeurs, depuis 2026, mentions légales</footer>`.
