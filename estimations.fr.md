C'est difficile de faire des prédictions, surtout dans l'avenir.
Et pourtant, tout le monde en veut.
En toute logique, vous avez besoin d'estimer les dates de sortie de très peu de fonctionnalités.
Mais puisqu'il faut souvent tout estimer par habitude, autant le faire rapidement.
La vie est trop courte pour gâcher votre jeunesse en divination.

Chez un précédent employeur, nous réussissions à faire de bonnes prédictions, de manière efficiente et efficace.
Il nous fallait en effet 2 ou 3 heures pour prédire plusieurs mois de release pour chaque équipe.
Et nos prédictions étaient plutôt bonnes, en comparaison des nombreuses organisations que j'ai connues, où les prédictions sont uniquement dérivées d'estimations de coûts.
Pour faire ces prévisions, nous nous basions autant que possible sur ce que nous avions fait par le passé.

# Contexte

Commençons par un disclaimer: je n'ai plus les chiffres, il va vous falloir vous contenter d'à peu près.

Ensuite le contexte.

Nous étions 3 ou 4 équipes à sortir 2 ou 3 produits sur étagère, plus ou moins liés entre eux. Les équipes étaient matures sur leurs périmètres fonctionnels.

Les dépendances avec d'autres équipes étaient extrêmement limitées. Nous y reviendrons en conclusion.

En arrivant, j'ai eu la bonne surprise de découvrir que les items de backlog étaient petits, c'est-à-dire terminés en 2-3 jours maximum. D'habitude, je dois d'abord travailler sur ce problème. Ici, c'était ancré chez les gens.

Tous les items réalisés par l'équipe étaient rattachés à des items plus gros.
Même les bugs (je ne comprends toujours pas la différence entre les bugs et le reste, je ne vois que des choses à faire, des écarts avec un idéal).
Jira oblige, ces gros items s'appelaient epic, même s'il a fallu travailler au fil des releases pour faire comprendre qu'un epic, pour être utile, doit avoir une fin.
Un epic embarquait environ 10 à 50 items plus petits.
Nous appellerons ces petits items des tickets.
Je me refuse à appeler les items plus petits des user stories, jira ou pas: une user story est une histoire, d'un utilisateur, point.
Une release devait embarquer une vingtaine d'epics.

Une release sortait tous les 3 à 6 mois.

A la fin d'une release, nous savions retrouver rapidement ce que l'équipe avait annoncé au début de la release.

Récapitulons. A la fin d'une release, nous savions:
- quels epics l'équipe avait annoncé en début de release,
- quels epics l'équipe a terminé,
- quels tickets l'équipe a réalisé dans chaque epic,

A partir de ça, nous pouvions préparer la release à venir:
- estimer les epics à faire,
- calculer la capacité de l'équipe pour la release, en tickets,
- calculer la proportion de capacité disponible pour les items prévus ou imprévus,
- ainsi, prédire un contenu pour la release.

# Estimation des epics

Etant donné que nous savions combien de tickets les epics terminés représentaient, nous les rangions dans des grosses catégories.
Les catégories suivantes sont suffisantes: 1, 3, 10, 30, 100, etc...
Dans ma carrière, j'ai vite réalisé que la suite de Fibonacci était trop précise.
La différence entre 1, 2, et 3 est insignifiante par rapport aux autres valeurs, par exemple.
Or, quand on prédit l'avenir, on ne veut pas laisser penser qu'on sait ce qu'on fait.
Dans le mot estimation, il y a estimation, il ne faut pas l'oublier.

Ensuite, nous prenions les epics à sortir à l'avenir.
Nous les prenions par ordre de priorité business (je ne m'étendrai pas sur ce sujet dans cet article).
Nous rangions chacun des epics dans une des boîtes.
Nous le faisions en comparant les epics avec ceux déjà réalisés.

Nous n'essayions surtout pas d'estimer combien de tickets il faudrait réaliser pour finir l'epic.
C'est justement là l'erreur à ne pas commettre: on veut éviter de prédire l'avenir.

Nous nous mettions d'accord par consensus.
Un règle simple pour régler les conflits: si nous pensions que ça ne rentrait pas dans une boîte, même presque, l'item passait dans la boîte supérieure.

Cet exercice prenait environ 1h.

# Capacité de l'équipe

C'est assez simple. Si dans la release précédente nous avions terminé 200 tickets, nous prévoyions d'en faire autant dans la suivant.

On peut faire un produit en croix si les durées des releases varient, mais il faut se méfier de tels calculs:
on a toujours des périodes plus ou moins exploratoires ou stables dans une release.

Appliquer un produit en croix en fonction du nombre de personnes, des disponibilités des individus, ou de leurs congés, est encore plus dangereux. Je préfère considérer l'équipe comme un tout. En effet, les délais d'attente expliquent beaucoup plus les délais que la capacité d'une équipe à paralléliser des tâches terminées correctement.

En fait, je pense que la fonction (temps de travail -> capacité de l'équipe) n'est pas calculable ou prédictible.
Elle n'est même pas croissante, peut-être pas continue, et surtout pas linéaire.
Ne tenez pas compte du temps de travail pour prévoir une capacité, ce sera plus simple.

Cet exercice prenait 15 minutes.

# Imprévu

En comparant ce que l'équipe avait annoncé avec ce qu'elle avait terminé, nous récupérions un taux d'imprévu.
Entre l'annonce d'une release et sa livraison, on change d'avis, repriorise, découvre des trous fonctionnels, de la dette technique, etc.
Et bien il n'y a aucune raison que ça change entre deux releases.
Nous considérions donc que le taux d'imprévu reste le même entre deux releases.

Nous nous limitions au tri des epics dans les catégories prévu ou imprévu.
Pas besoin de catégoriser les tickets d'un epic.

Notez que nos proportions d'imprévus étaient comprises entre 65% et 75%.
C'est à dire que 65 à 75% de ce que nous faisions dans une release était imprévu.
C'est comme ça, il faut prendre les chiffres tels qu'ils sont et ne pas essayer de tordre la réalité.
Il ne faut pas non plus faire du planning dirigé par l'espoir, en décrétant fermemant que la prochaine fois on ne changera pas d'avis.
C'est une bonne nouvelle de tenir compte de l'information qu'on découvre au fur et à mesure.
Si vous avez peu d'imprévus, ne prenez surtout pas ça pour une bonne nouvelle sans y réfléchir.
Il y a de grandes chances que quelqu'un se voile la face, ou, comme les 3 singes, ferme toutes les écoutilles en criant lalalalalala prostré dans le coin d'une salle de meeting.

Cet exercice prenait environ 1 heure, en fonction de la difficulté des fouilles archéologiques.

# Prédiction

Nous avions la capacité de l'équipe, et un taux de prédiction juste. Avec ça, nous connaissions notre capacité pour les tickets prévus.
Par exemple, si dans la précédente release nous avions réalisé 400 tickets dont 100 annoncés, alors nous avions une capacité de tickets de 100 tickets prévus au départ de la release suivante.
Et avec l'estimation des epics en nombre de tickets, nous savions quels epics nous pouvions annoncer pour la release suivante.
Et voilà, à vous de trouver la bonne méthode pour votre contexte.

# Turtles all the way

Notez que ce que nous faisions pour une release peut s'adapter à d'autres niveaux de granularité.
Nous en utilisions d'ailleurs une variante pour les itérations (en remplaçant les epics par les tickets).

La seule chose à savoir, c'est que le pourcentage d'incertitude doit être calculé indépendamment pour chaque niveau de granularité.
Savoir qu'on a 75% d'incertitude au niveau de la release ne permet pas de prédire l'incertitude pour une itération, et vice versa.
On peut avoir plus ou moins d'incertitude à un niveau de granularité plus petit.

# Explication

Pourquoi cette méthode fonctionnait-elle dans notre contexte ?

Tout d'abord, nous sommes tombés sur le bon niveau de granularité.
Comme tous les systèmes imbriqués, il peut exister un niveau stable, c'est à dire prédictible.
Dans notre cas, le niveau stable était celui des epics pour la release, et des tickets pour les itérations.
Nous avons eu la chance d'avoir un système avec des niveaux stables, et de les trouver du premier coup.

Ensuite, nous en avons parlé, parce que les dépendances étaient très peu nombreuses.
La charge de travail expliquait donc la majorité du délai de livraison.
C'est rarement le cas.
En général, les items passent leur temps dans des queues.
Dans ce cas, il est inutile d'estimer la charge de travail, même par comparaison.
Il faut plutôt mesurer les lead times, et estimer les dates de livraison en fonction.

Je pense que le fait d'avoir beaucoup de petits tickets par epic permettait aussi de lisser les disparités, par la loi des grands nombres.
A l'échelle des epics, et étant donné les erreurs inhérentes à la divination, nous pouvions considérer les tickets comme identiques.
