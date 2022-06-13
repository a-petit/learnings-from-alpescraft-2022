# Introduction au T(ype)DD avec F#

## Speakers
- Florent Pellet (Software Crafter Lyon, DDD Lyon, MUG Lyon, HackYourJob, Superindep.fr)
- Clément Bouillier (Superindep.fr)
- Dispos pour des BBL

## Talk

Sujet : tennis kata (calcul du score d’un match)

Solution 1 en C# : attention aux invariants !
Solution 2 en C# : plus de classes, plus de code aussi.

Peut-on faire mieux avec des systèmes de Type ?

Type = feedback encore + rapide qu'un test.

Le typage réduit le nombre de tests à réaliser.

Types algébriques
- types OU : ScorePlayer = Love | Fifteen | Thirty | Forty | Advantage | Game
- types ET : Score = ScorePlayer * ScorePlayer

Il est possible de représenter des structures complexes avec cela.

Estimer / réduire la cardinalite : 
- card(ScorePlayer) = 1 + 1 + 1 + 1 + 1 + 1 = 6
- card(Score) = 6 * 6 = 36

## Solution F#

- découpage en PlayerScore ; Score ;
- D’abord 6, 6x6 mais cas interdit !!
- Suppression de advantage et game de player score.
- Il reste le cas égalité !!
- Pas otherPoint(forty, forty) -> deuce

Intérêt de l'approche : 
- Construction des types au fil de la prise de note avec le métier

## Conclusion : 

Le typage et la prog fonctionnelle : 
- les invariants sont sécurisés directement par le typage
- La boucle de feedback du REPL est encore meilleure que celle du TDD
- très pratique pour la prise de note
- amène des solutions compactes. 

Pour aller + loin : 
- F# for fund and profits (5 étoiles)

TODO : 
- le faire simplement en mode objet
- refaire le kata en F#
- récupérer le liens vers le répo GIT
