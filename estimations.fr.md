C'est difficile de faire des prédictions, surtout dans l'avenir.
Et pourtant, tout le monde en veut.
En toute logique, vous avez besoin d'estimer les dates de sortie de très peu de fonctionnalités.
Mais puisqu'il faut souvent tout estimer par habitude, autant le faire rapidement.
La vie est trop courte pour gâcher votre jeunesse en divination.

Chez un précédent employeur, nous réussissions à faire de bonnes prédictions, de manière efficiente et efficace.
Il nous fallait en effet 2 ou 3 heures pour prédire plusieurs mois de release pour chaque équipe.
Et nos prédictions étaient plutôt bonnes, en comparaison des nombreuses organisations que j'ai connues, où les prédictions sont uniquement dérivées d'estimations de coûts. Pour faire ces prévisions, nous nous basions autant que possible sur ce que nous avions fait par le passé.

Commençons par le contexte qui fait que cette méthode était possible. Non, commençons par un disclaimer: je n'ai plus les chiffres, il va vous falloir vous satisfaire d'à peu près. Ensuite le contexte: nous étions 3 ou 4 équipes à sortir 2 ou 3 produits sur étagère, plus ou moins liés entre eux.

Les dépendances avec d'autres équipes étaient extrêmement limitées. Si les dépendances avaient été plus importantes dans la justification des délais, il aurait été inutile de faire des calculs basés sur les coûts.

J'ai eu la bonne surprise en arrivant de découvrir que les items de backlog étaient petits, c'est-à-dire terminés en 2-3 jours maximum. D'habitude, je dois d'abord travailler sur ce problème. Ici, c'était ancré chez les gens.

Tous les items réalisés par l'équipe étaient rattachés à des items plus gros.
Même les bugs (je ne comprends toujours pas la différence entre les bugs et le reste, je ne vois que des choses à faire, des écarts avec un idéal).
Jira oblige, ces gros items s'appelaient epic, même s'il a fallu travailler au fil des releases pour faire comprendre qu'un epic, pour être utile, doit avoir une fin.
Un epic embarquait environ 10 à 50 items plus petits.
Nous appellerons ces petits items des tickets.
Je me refuse à appeler les items plus petits des user stories, jira ou pas: une user story est une histoire, d'un utilisateur, point.
Une release devait embarquer une vingtaine d'epics.

Une release sortait tous les 3 à 6 mois.

A la fin d'une release, on savait retrouver rapidement ce que l'équipe avait annoncé au début de la release.

Récapitulons. A la fin d'une release, on sait:
- quels epics l'équipe avait annoncé en début de release,
- quels epics l'équipe a fini,
- quels tickets l'équipe a réalisé dans chaque epic,

A partir de ça, on peut préparer la release à venir:
- estimer les epics à faire,
- calculer la capacité de l'équipe pour la release, en tickets,
- calculer la proportion de capacité disponible pour les items prévus ou imprévus,
- ainsi, prédire un contenu pour la release.

#Estimation des epics

Etant donné que nous savions combien de tickets les epics terminés représentaient, nous les rangions dans des grosses catégories.
Les catégories suivantes sont suffisantes: 1, 3, 10, 30, 100, etc...
J'ai vite réalisé que la suite de Fibonacci est trop précise.
La différence entre 1, 2, et 3 est insignifiante par rapport aux autres nombres, par exemple.
Or, quand on prédit l'avenir, on ne veut pas laisser penser qu'on sait ce qu'on fait.
Dans le mot estimation, il y a estimation, il ne faut pas l'oublier.

Ensuite, on prend les epics à sortir à l'avenir.
On les prend par ordre de priorité business.
On range chacun des epics dans une des boîtes.
On le fait en comparant les epics avec ceux qui ont déjà été réalisés.
On n'essaie pas d'estimer combien de tickets il faudra réaliser pour finir l'epic.
C'est justement là l'erreur à ne pas commettre: on veut éviter de prédire l'avenir.
Les participants se mettent d'accord par consensus.
La règle est: si on pense que ça ne rentre pas dans une boîte, même presque, ça passe dans la boîte supérieure.

Cet exercice prend environ 1h.

#Capacité de l'équipe

C'est assez simple. Si dans la dernière release on a fait 200 tickets, on prévoit d'en faire autant dans la prochaine.
On peut faire un produit en croix si les durées des releases varient, mais il faut se méfier de tels calculs:
on a toujours des périodes plus ou moins exploratoires ou stables dans une release.

Appliquer un produit en croix en fonction du nombre de personnes, des disponibilités des individus, ou de leurs congés, est encore plus dangereux. Je préfère considérer l'équipe comme un tout. En effet, les délais d'attente expliquent beaucoup plus les délais que la capacité d'une équipe à paralléliser des tâches terminées correctement.

Cet exercice prend 15 minutes.

#Imprévu

En comparant ce que l'équipe avait annoncé avec ce qu'elle a fait, on récupère un taux d'imprévu.
Depuis l'annonce de la release, on a changé d'avis, repriorisé, découvert des trous fonctionnels, de la dette technique, etc.
Et bien il n'y a aucune raison que ça change.
Donc pour la prochaine release on considèrera que le taux d'imprévus sera le même.
Notez que nos proportions d'imprévus étaient entre 65% et 75%.
C'est à dire que 65 à 75% de ce qu'on faisait dans une release était imprévu.
C'est comme ça, il faut prendre les chiffres tels qu'ils sont et ne pas essayer de tordre la réalité.
Il ne faut pas non plus faire du planning dirigé par l'espoir, en décrétant fermemant que la prochaine fois on ne changera pas d'avis.
En effet, c'est une bonne nouvelle de tenir compte de l'information qu'on découvre au fur et à mesure.

On se limitait au tri des epics dans les catégories prévu ou imprévu.
Pas besoin de trier les tickets d'un epic.

Cet exercice prend environ 1 heure, en fonction de la facilité des fouilles archéologiques.

#Prédiction

On a la capacité de l'équipe, et un taux de prédiction juste. Avec ça, on connaît notre capacité pour les tickets prévus.
Par exemple, si dans la dernière itération on a réalisé 400 tickets dont 100 annoncés, alors on a une capacité de tickets de 100 tickets prévus au départ de la release.
Et avec l'estimation des epics en nombre de tickets, on sait quels epics on peut annoncer pour la prochaine release.
Et voilà, à table.

#Turtles all the way

Notez que ce qu'on faisait pour une release peut s'adapter à d'autres niveaux de granularité.
On l'utilisait d'ailleurs pour les itérations.
La seule chose à savoir, c'est que le pourcentage d'incertitude doit être calculé indépendamment pour chaque niveau de granularité.
Savoir qu'on a 75% d'incertitude au niveau de la release ne permet pas de prédire l'incertitude pour une itération, et vice versa.
On peut avoir plus ou moins d'incertitude à un niveau de granularité plus petit.

#Explication

Pourquoi cette méthode fonctionnait-elle dans notre contexte ?

Tout d'abord, nous sommes tombés sur le bon niveau de granularité.
Comme tous les systèmes imbriqués, il peut exister un niveau stable, c'est à dire prédictible.
Dans notre cas, c'était le niveau des epics pour la release, et les tickets pour les itérations.
Nous avons eu la chance d'avoir de tels niveaux, et de les trouver du premier coup.

Ensuite, nous en avons parlé, parce que les dépendances étaient très peu nombreuses, la charge de travail est ce qui explique la majorité du temps de réalisation.
C'est rarement le cas. En général, les items passent leur temps dans des queues.
Dans ce cas, il est inutile d'estimer la charge de travail, même par comparaison.
Il faut plutôt mesurer les lead times, et estimer les dates de livraison en fonction.

Je pense que le fait d'avoir beaucoup de petits tickets par epic permet aussi de lisser les différences, par la loi des grands nombres.
A l'échelle des epics, et étant donné les erreurs inhérentes à la divination, les tickets sont considérés comme identiques.
