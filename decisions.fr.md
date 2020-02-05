> _Vendredi 21h, en salle de réunion Henri Salvador._  
> — _Pluto Krath:_ Non non, il est hors de question de revenir là-dessus.
On avait décidé qu'on n'utiliserait pas de base de données, on ne va pas changer d'avis tous les quatre matins.  
> — _Nadia:_ On n'avait pas pensé qu'on devrait naviguer dans des données qui ne rentrent pas en mémoire.
Si on n'a pas de base de données, on va devoir implémenter tout ce dont on a besoin pour faire ça depuis le disque: indexation, requêtes relationnelles, plans d'exécution, sérialisation...
Si on avait adopté une base sans t'en parler tu ne l'aurais même pas remarqué.  
> — _Pluto Krath:_ Non, on a décidé qu'on n'utilise que la mémoire et le disque dur, on reste comme ça.
Implémentez ce dont vous avez besoin.

Je suis régulièrement confronté avec ce genre de non sens.
Dans les organisations, il y a un fétiche de la décision.
Des gens, généralement influents, ont dépensé du temps et de l'énergie, négocié, se sont impliqués, pour que les réunions accouchent de résultats, de plans d'action, de décisions.
Vous remarquerez que je parle de réunions.
Car bien souvent, ces décisions sont prises hors sol, souvent même avant de démarrer quoi que ce soit.
C'est à dire qu'elles ne sont pas difficiles à modifier.
Et pourtant, on s'y accroche.

Qu'est-ce qu'une décision ?
Comme le dit l'adage, décider c'est renoncer.
Une décision, c'est couper les branches d'un arbre de décision, abandonner des options.
Corollaire: pour garder les options ouvertes, il faut prendre le moins de décisions possible, le plus tard possible.
On parle de "last responsible moment".
Tous les mots de cette expression sont importants.

Une décision est un choix entre plusieurs branches.
Et c'est aussi, on l'oublie trop souvent, le choix de couper des branches maintenant ou pas.
On peut aussi attendre.
On considère que ne pas prendre de décision représente un risque.
Mais quid d'abandonner une possibilité ?
On voit bien qu'il faut savoir pourquoi on laisse tomber une option, non ?
"Savoir pourquoi", c'est le coeur du sujet.

Abandonner une option suppose de comprendre pourquoi.
Idéalement, on dispose de données objectives et indiscutables pour chiffrer telle ou telle option, et savoir laquelle prendre. Malheureusement, la différence entre la théorie et la pratique est la pratique, et on a rarement cette chance.
En général, on se base au mieux sur des estimations, en tout cas sur des hypothèses.
De toute façon sur des informations incomplètes.
Et évidemment, sur des piles de biais cognitifs, bien trop nombreux et puissants pour être listés ici.

Quoi qu'il en soit, ce qui compte, c'est de savoir si la décision est irrémédiable.
Finalement, si un choix est réversible, on peut le prendre facilement, ça n'entraîne aucun risque.
Or il est souvent facile de rendre une décision réversible. Une non-décision, quoi.
C'est ma stratégie préférée.

Au final, le coeur d'une décision est d'en soupeser les risques, et d'essayer de les limiter.
D'un côté, on a le risque de ne pas prendre de décision, c'est à dire de bloquer l'avancement d'une tâche.
De l'autre, on a le risque de couper une option qui peut s'avérer être bien meilleure.

Mes stratégies pour limiter les risques d'une décision sont:
- comme pour tout, demander pourquoi. Encore et encore.
Pour quelles raisons souhaite-t-on naviguer dans des grosses quantités de données ?
De quelle genre de navigation parle-t-on ?
Quelles sont les contraintes, les -ities ?
- limiter les conséquences de la décision.
Au lieu de couper une grosse branche, on essaie de couper une branchounette.
Par exemple, dans le choix de la base de données, on peut commencer par tester une base de données gratuite, voire in-memory, ou de la simple indexation. Ou encore ne pas s'attaquer à la concurrence d'accès tout de suite.
On peut aussi commencer par faire les tests sur une copie des données de production, au lieu de prendre le risque de les altérer.
- vérifier les hypothèses.
Pourquoi Pluto a-t-il "décidé de ne pas prendre de base de données ?
Je suppose qu'il s'attend à payer des licences, ou à avoir affaire avec une équipe de DBA butés, gérés par un manager qui fait de l'ombre à sa carrière.
- lister les raisons de ne pas décider, et les raisons de choisir telle ou telle branche.
Par exemple, une base relationnelle a des limitations en terme de scaling, mais offre le relationnel et le transactionnel, alors qu'implémenter les plans d'exécution a pris plusieurs dizaines d'années à des gens qui comprennent de quoi ils parlent.
- lister les résultats prévus de ne pas décider, et de choisir chaque branche.
Par exemple, si on ne décide pas tout de suite, on peut s'attaquer à un autre problème en premier, sans risquer de devoir merger une énorme modification structurelle du produit.
Une base relationnelle convient bien à un modèle relationnel.
D'autres modèles vont bien... avec d'autres modèles.

Quelques commentaires pour finir sur les décisions.

Beaucoup d'équipes suggèrent de tenir un journal des décisions.
Je n'ai jamais eu l'occasion de pratiquer cela, mais je crois effectivement que ça peut énormément aider les organisations, notamment en offrant une base objective pour contourner les biais cognitifs.
Les interwebs proposent de nombreux templates.
Il s'agit de trouver un format commun à vos décisions, en listant par exemple le problème à résoudre, les options, les hypothèses, les raisons de la décision, les résultats espérés, les risques anticipés, etc.
Un journal permet d'évaluer les décisions passées, dans leur contexte, et d'améliorer la prise de décision.

Juger une décision ne dépend pas que des résultats.
Une décision peut être excellente et entraîner de mauvais résultats, ou à l'inverse, être stupide et aboutir à des résultats géniaux.
Juger une décision suppose de la regarder dans le contexte dans laquelle elle a été prise.

Il existe plusieurs cadres pour officialiser la décision, comme l'autocratie, le consensus, le consentement, l'anarchie.
Ma préférence va vers le consentement, où on autorise par défaut les gens à faire ce qu'ils veulent, sauf objection explicite.
Ca suppose de savoir limiter les conséquences potentielles d'une décision.
Quoi qu'il en soit, sachez que la préférence de votre organisation n'est pas la seule possibilité, et qu'il existe d'autres stratégies.

Il est intéressant de prendre du recul sur vos décisions.
Quelles sont les dernières décisions que vous avez prises ?
Qui ont été prises pour vous ?
Quelles étaient les options ?
La décision était-elle à prendre maintenant ?
Faites cet exercice, vous découvrirez des possibilités dont vous n'aviez pas idée.
