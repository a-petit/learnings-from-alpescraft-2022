# TDD et la triche

Jonathan Laurent

Sujet = BowlingKata

Solutions :
- démo d’uncle bob
- version triche par Jonathan

Idée : 
1. Construire un cas de test le plus riche possible et noter de la valeur finale. 
2. Tricher. 
3. Clarifier : décomposer, faire émerger le code à travers le refactoring de l’**implementation** et du **test**.

Exemple : 
1. Simuler une partie de Bowling avec coups normaux, strikes, spares, ... et noter le score final (imaginons 88).
2. Ecrire un test qui calcul le score d'une partie. Renvoyer 88. On passe au vert. 20 secondes.
3. Clarifier en décomposant. C'est quoi 88 ? C'est 2 + 4 + 5 + ... + 10 + ... C'est scoreRoll + scoreBonus. ...

Méthodes : 
- Extract variable. Extract variable.
- Extract variable. Extract variable.
- Identifier les motifs.

Limites : 
- Nécessite d’avoir une bonne connaissance du métier. 

Remarques : 
- 1 seul test = cas extrême. Si toutes les informations pas condensables dans un seul test, on peut créer plusieurs tests. Mais bien commencer par tricher avec l'ensemble des tests avant de refactorer.
- Pour valider la solution, il est important de rajouter un test de triangulation après la phase de triangulation. Ce test doit passer directement !

Attention : 
- si tu te trompe sur le métier et que la triangulation échoue, il est alors nécessaire de répartir de zéro.
- Kata pour mettre en évidence l’importance de la clarification. C'est une curiosité poussée à l'extrême. Ne pas faire en production ^^.

Conclusion : 
- importance de la clarification dans la phase de refactoring !