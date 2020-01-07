#Les poupées russes n'ont pas de nom

Les modèles mentaux vous aident à prendre des décisions quand ils correspondent à la réalité à laquelle vous avez à faire face.
Beaucoup de modèles sont trop simplistes pour représenter un panel de situations suffisant.

Un grand nombre de modèles représente des systèmes imbriqués.
Dans certains d'entre eux, chacun de ces systèmes a un nom, et est décrit indépendamment.
Il est préférable de décrire les caractéristiques d'un système en rendant cette explication la plus adaptable possible au contexte.
Quand vous nommez une couche, votre catégorisation devient difficile à adapter.
Plus vous rencontrez de situations, plus vous les incorporez dans vos modèles, en rendant les caractéristiques du système génériques.
C'est un peu comme dans TDD avec design émergent: [au fur et à mesure que le code de test devient spécifique, le code de prod devient générique](https://sites.google.com/site/unclebobconsultingllc/home/articles/as-the-tests-get-more-specific-the-code-gets-more-generic).
Cyrille Martraire parle d'[élever la ligne de flottaison](https://youtu.be/svh_NxbOJV8), de la théorie à la concision, en liant ceci à la paresse (ce qui est bien dans l'ingénierie).
Comme dans le refactoring, ce n'est pas simple.
Cela suppose d'incorporer les différentes caractéristiques d'une couche dans un vocabulaire commun qui fait sens.

Par exemple, le manifeste agile distingue:
- les valeurs, qui sont acquises,
- les principes, directement dérivés des valeurs, dans le contexte que les auteurs connaissaient à l'époque,
- les pratiques, dérivées des principes.
On pourrait continuer à l'infini. Sauf que plus on dérive des règles dans un contexte, plus on devient dépendant du contexte.
Il se trouve que les pratiques on beaucoup de mal à résister au test du temps, alors que les valeurs peuvent toujours être considérées comme valides dans la plupart des organisations, voire révolutionnaires dans beaucoup d'autres.
On peut considérer les valeurs agiles comme une abstraction des principes agiles, ou les principes comme une instanciation des valeurs dans un contexte donné.
On peut utiliser les valeurs pour penser une situation avec un large point de vue. Et les principes pour nous guider dans des contextes plus concrets.

Regardons quelques exemples plus précisément.

##Backlog

Une roadmap inclut des objets de granularités différentes.
Les utilisateurs à courte vue de jira utilisent les tâches, puis les stories, puis les epics.
Ils différencient rarement ces catégories, et utilisent aveuglément ce que jira propose par défaut, en tordant ces catégories à leur process existant.
Même si c'est généralement une mauvaise idée d'utiliser un outil sans chercher à le comprendre, il est vrai qu'on peut extraire des règles plus générales pour décrire ces différentes catégories, depuis la stratégie, ou même les valeurs, de l'entreprise, jusqu'à des tâches individuelles.
![John Cutler à propos de la cohérence souhaitable, depuis les tâches jusqu'aux objectifs long terme](https://twitter.com/johncutlefish/status/1158817067056812033/photo/1)
Si nous appelions cette généralisation un but ([ou une opportunité, ou un pari](https://www.infoq.com/presentations/bets-boards-missions-agile/)), cette généralisation pourrait ressemble à:
- un but a une fin
- on sait comment un but évolue en vérifiant son impact
- un but peut être composé de buts imbriqués
- le pourquoi d'un but imbriqué est le comment du but englobant
- on doit revoir l'énoncé d'un but à intervalle régulier
Vous avez remarqué que je décrivais les propriété d'un système de manière à le tester en property-based testing ?

##Double boucle d'apprentissage

Quand vous développez un système, vous le faites en découvrant les besoins des utilisateurs. C'est la première boucle.
Ensuite, vous améliorez votre process en apprenant comment vous travaillez en tant qu'équipe.
Ensuite, vous apprenez à améliorer votre process.
Ainsi de suite, jusqu'à ce que deux boucles consécutives se confondent.
Ces boucles on des propriétés communes. Par exemple:
- on veut garder suffisamment de place pour apprendre et s'adapter
- le process d'apprentissage évolue
- on tient compte de l'incertitude
- dans la mesure du possible, on veut diminuer l'incertitude en utilisant un processus scientifique
On peut maintenant dériver ces règles pour le contexte de chaque boucle.

##la pyramide des tests

La [pyramide des tests](https://www.mountaingoatsoftware.com/blog/the-forgotten-layer-of-the-test-automation-pyramid) suppose que vous avez trois couches: tests unitaires, de service, et d'IHM.
Certains adaptent la pyramide à leur vocabulaire, en ajoutant ou renommant des couches.
Quoi qu'il en soit, dès que votre système se complexifie un tant soit peu, la réalité demande un peu plus de nuances que ça.
La plupart du temps, vous finissez par avoir plusieurs modules, chacun ayant ses couches.

Vous voulez trouver le meilleur compromis, pour chaque test, entre:
- le réalisme: si le test passe, alors le cas d'utilisation correspondant passera, de bout en bout, en production.
- la rapidité: des milliards de tests doivent s'exécuter en quelques nanosecondes.
- la couverture: vous voulez tester chaque cas particulier, imaginable ou non.
- la fiabilité: un test ne doit échouer que si la fonctionnalité correspondante n'est pas fournie. En général, [un test est solide s'il embarque peu de choses](https://testing.googleblog.com/2017/04/where-do-our-flaky-tests-come-from.html).
- l'explicabilité: un test doit clairement indiquer pourquoi il échoue.
- et beaucoup d'autres.

Pour une couche donnée d'un module donné, vous trouverez le bon compromis de pratiques.
Ce compromis vous permettra d'exécuter des tests dans une gamme de valeurs, pour chacune des propriétés citées ci-dessus.
Dans l'espace multidimensionnel des propriétés de tests, ça vous donnera une bulle. Cette bulle correspond à un jeu de pratiques.
Si vous généralisez ceci, vous obtenez une bulle pour chaque couche de chaque module.

Par exemple, pour certains tests, vous pouvez décider de mocker/stubber/faker/... telle ou telle librairie. Alors que pour d'autres, vous pouvez préférer utiliser sa véritable implémentation.
Pour telle fonctionnalité, pour pouvez vous limiter à un smoke test pour vérifier la plomberie, tout en générant 5000 test par seconde pour les cas aux limites, en ne testant que la sous-sous librairie métier.
Ca dépend.

Dans un système simple, vous pourrez sûrement appeler une bulle tests unitaire, d'intégration, système, IHM, ou de bout en bout, de manière à ce que ça ait du sens pour l'ensemble de vos modules.
Dans des systèmes plus complexe (par exemple polyglotte), ce que vous appelez test unitaire sera totalement différent d'un module à l'autre.

De plus, comme pour tout système, l'architecture est imbriquée.
Le test d'intégration d'un système est le test unitaire d'un système de plus haut niveau.

Par exemple, quand vous codez, il est assez probable que vous utilisiez l'addition de deux entiers.
Cette opérateur fait partie du système que vous codez, même si vous l'embarquez par le langage.
Et pourtant vous n'écrivez pas de test unitaire pour cet opérateur. Vous l'utilisez comme s'il fonctionnait comme vous le pensez.
Pour autant, des gens ont testé l'addition.
Au niveau hardware, vous pouvez même considérer qu'il ont exécuté des tests d'intégration, qui embarquent les invalidations de cache au niveau CPU et bien d'autres choses.
Et vous testez probablement cet opérateur indirectement, soit par test d'intégration, ou ce qu'on appelle naïvement test unitaire.

Si vous donnez un nom à chaque couche de test, vous devez, pour chacune d'entre elles:
- en énumérer les propriétés
- en définir les jeux de pratiques et d'outils
- trouver une catégorie pour chaque couche que vous rencontrez
Mais vous ne pouvez pas savoir à l'avance de combien de couches vous aurez besoin.
Vous découvrirez ces besoins au fur et à mesure.
Et de toute façon, ces différentes catégoriesne sont même pas des couches hiérarchiques, mais un graphe de bulles plus ou moins reliées par des propriétés, des outils, et des pratiques, communs.

Pour toutes ces raisons, je préfère rester sur la notion floue de bulles de propriétés, outils, et pratiques.
J'adapte ce concept à chaque contexte, en recherchant, nommant, et décrivant, ces bulles.
Ca m'évite de devoir tordre la réalité pour la faire rentrer dans la pyramide, et ça réduit donc le poids du sang dans mon cerveau.
Oh, et avoir un jeu de bulles définies pour un produit donné ne vous empêche pas d'en définir de nouvelles, si ça peut aider.

##Conclusion

Penser les systèmes imbriqués comme des couches indépendantes peut vous aider à découvrir un nouveau sujet en vous donnant des cas concrets.
Toutefois, vous pouvez rapidement réaliser que ces couches hardcodées ont besoin d'évoluer pour correspondre à votre contexte.
Généraliser une catégorisation vous aide à raisonner sur une activité d'une manière unifiée.
Vous ne voulez pas pour autant merger tous les systèmes imbriqués dans une description unique.
Ce serait une description fractale, et ce serait une vue simpliste de l'univers.
Vous voulez vous faciliter la vie, en ayant une vue commune à haut niveau, tout en étant capable de zoomer quand vous en avez besoin.
Abstraire un de jeu de catégories diminue le poids du sang dans votre cerveau.
