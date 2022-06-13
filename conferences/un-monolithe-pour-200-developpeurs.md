# Monolith pour 200 développeurs : avantages et défis

David Gageot, Chief Architect @ Doctolib

Retours d'expérience post-vaccination


## Boring architecture

PostgreSQL, Ruby on rails, monolith.

## 1
- 1 répo
- 1 base de données
- 1 processus de déploiement
- 1 service à monitorer.

Pas d’éparpillements.

Microservices : on oublie toujours les inconvénients !!!

Pendant la vaccination : 
- passage de 1 -> 3 mep par jour
- on peut faire mieux, mais 1 MEP par jour reste déjà une belle performance

Monobase 25 To :
⁃ 1 writer, 13 reader
⁃ tests de charge : x2, si ça tient, on a 6 mois devant nous
⁃ pb : x5 en un jour
⁃ 6 mois ça peut être trop long

Tu peux être pragmatique. Il y a toujours un moment où ça va péter. 

## Organisation des équipes

Organisation classique : feature team, teams of teams. Simple

Plein de personnes qui arrive avec des nouvelles idées. C'est un effort de tous les jours de reexpliquer, défendre la solution. **Les optimums locaux ne correspondent pas forcément l'optimum global**. Quand une personne a des véléités de changement : "présente moi tous les inconvénients de ta solution". Si l'idée n'est pas retenue, la discussion a lieu.

Actuellement : 
- monilith (charge cognitive, complexité du code, plus de produits)
- évolution en cours vers un modular monolith

Faire du craft avec 200 personnes : c’est lent

Tech radar

Truc marrant : le système vu par les différents pôles. Dev, marketing, data, sécurité, ...

## Tests

Principalement des tests end to end (40k)
La CI parfois mise à mal si trop de pushs

Just in time = parfois trop tard. On veut toujours garder des portes ouvertes.

Jusqu'à il n'y a pas longtemps : 
- tous les tests étaient exécutés à chaque push
- durée de la campagne de tests : 30 minutes

La facture commençait à gonfler. 
- Affinage : test sur les parties modifiées uniquement (+ complexe, mais nécessaire)0

Post-vaccination : Retours au fondamentaux : 
- simplicité
- incréments

## Résumé :

⁃ la CI a été bien secouée pendant la vaccination (très très forte montée en charge, non anticipée)
⁃ l'optimum de la boîte n'est pas forcément les optimum locaux
⁃ convaincre de la pertinence du monolith est un effort de tous les jours. "Est-ce que tu as bien pensé à tous les inconvénients (MEP, crises, merge, recrutement, …) ?"

Remarque : rollback en mono = facile !

## Q/R

⁃ feature branching (branche de courte durée)
⁃ outils d’analyse statistique
⁃ robot qui empêche certaines erreurs déjà produites
⁃ Déclenchement sélectif : relation inversée de la couverture de test sur les fichiers modifiés. Un peu trop hi tech à leur goût mais simple. Coût cognitif nul pour les développeurs
⁃ e2e : capi bara, sélénium, …

Est-ce que tu as bien pensé à tous les inconvénients (MEP, crises, merge, recrutement, …)