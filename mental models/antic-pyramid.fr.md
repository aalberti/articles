A l'approche de son bureau, Pluto Krath courait presque de colère dans son bureau. Il n'entendit pas la voix qui en sortait.

— K.I.T.T, rappelle-moi d'acheter du lait en rentrant à F.L.A.G.

Il entra dans la pièce et poussa son ordinateur sur son bureau:

— Qu'est-ce qu'ils ne comprennent pas à la pyramide des tests? Même un enfant comprendrait.

Il se tourna et s'immobilisa, ses yeux hurlant, sa bouche fermée par professionalisme.

— Qu'est-ce que tu fais ici David ?

Sur son affiche de Sharknado The 4th Awakens, il manquait [encore](https://www.arolla.fr/blog/2020/03/retour-de-decision/) le colonel Shepard. David Hasselhoff se tenait près de la fenêtre. Il leva sa montre près de sa bouche.

— Laisse tomber le lait, K.I.T.T. Je vais en avoir pour un moment.
— _Très bien, Michael_
— Et maintenant tu sors de K2000, fabuleux. Absurde jusqu'au bout des ongles.
— Alors comme ça la pyramide des tests, hein ?

Pluto s'assit.

— Très bien, admettons. Les développeurs ne la comprennent pas. Notre campagne de tests automatique prend une éternité, et les tests unitaires laissent passer trop de bugs. J'essaie de leur expliquer comment faire des tests unitaires, de service, ou d'IHM, et ils me répondent sans cesse "ça ne marchera pas ici". Combien de fois j'ai entendu ça.

David se tourna vers la fenêtre.
— [La pyramide des tests](https://www.mountaingoatsoftware.com/blog/the-forgotten-layer-of-the-test-automation-pyramid). Ca c'était une belle métaphore. Beaucoup de tests unitaires, peu de tests de bout en bout. Tu as raison, tout le monde comprend ça. Tu dois mal t'y prendre. Qu'as-tu dit pour qu'ils te suivent?
— Je leur ai dit que pour avoir une campagne plus rapide, ils devaient transformer plus de tests d'intégration en tests unitaires. Ca leur permettrait de tester plus de cas aux limites, et donc de rendre le produit plus robuste.

David se tourna à nouveau vers Pluto.
— Les test d'intégration font partie de la pyramide?
— Non, l'article de Mike Cohn parle des tests unitaires, de service, et d'IHM. Toi-même tu as parlé de tests unitaires et de tests de bout en bout.

[![The test pyramid](http://www.mountaingoatsoftware.com/uploads/blog/Testpyramid.jpg)](https://www.mountaingoatsoftware.com/blog/the-forgotten-layer-of-the-test-automation-pyramid)

David fit un clin d'oeil à Pluto.
— Oups, j'ai utilisé le mauvais terme. En fait, je n'ai jamais vraiment compris la pyramide des tests. Et tu n'as pas compris que je n'ai pas compris. Donc je me demande ce que tu as compris que l'équipe n'a pas compris. Les mots sont importants pour expliquer les choses. Dans le logiciel, tout est dans le détail.
— Oh pitié, tout le monde sait ce qu'est un test unitaire. Tu testes une méthode ou une fonction, sans faire d'I/O. Ca rend le test rapide, et tu peux en faire tourner des dizaines de milliers en quelques secondes.
— Et les tests de services ? d'intégration ? de système ? de bout en bout ? d'IHM ? Je peux te sortir plusieurs pyramides alternatives qui parlent de ces types de tests. Parce que l'originale devait être adaptée à d'autres contextes. Et aucune de ces alternatives ne fait consensus. En passant, je peux aussi t'assurer que les défenseurs les plus célèbres du test unitaire n'ont jamais réussi à se mettre d'accord sur une définition de ce que ça peut être.
— Très bien, on peut chipoter. En attendant, la pyramide des tests ne m'a jamais trahi. Dans toutes les équipes auxquelles j'ai participé, nous séparions 2 ou 3 catégories de tests, et nous avions toujours une campagne de tests automatiques solide. J'essaie juste de partager mon expérience avec l'équipe.
— Voici d'autres propriétés communes de tes expériences passées: c'était des petits monolithes d'école, avec très peu de dépendances sur d'autres équipes. Le premier était un logiciel d'achat Spring/react d'école, et le deuxième était un batch quotidien d'aggrégation de fichiers d'école. Et surtout, aucun de ces produits n'était votre produit actuel. Le contexte fait tout. En quoi votre produit est-il différent?

Pluto s'appuya sur son bureau. Il devint soudain plus enthousiaste.
— C'est un ensemble de 17 micro-services, développés dans plusieurs languages, parfois par des personnes externes à l'équipe. Ses fonctionnalités dépendent parfois d'autres équipes. Il est distribué, tourne en 24/7, et les micro-services peuvent être déployés indépendamment les uns des autres.
— ... et les micro-services sont plus ou moins proches du système, plus ou moins exigeants en terme de performance, développés à différentes époques, ont différents niveaux de maturité, dépendent plus ou moins d'arborescences de fichiers ou de la planification d'exécution de scripts. Ils sont parfois scindés, leurs interfaces évoluent, au fur et à mesure que l'équipe comprend ce qu'elle doit ou peut faire.
— Quel est le rapport avec des tests unitaires ou de services ?
— Et bien qu'appelles-tu le service à tester ? Le service à l'utilisateur, aux frontières du produit, ou l'interface http du micro-service ? Qu'appelles-tu une méthode ou une fonction à tester unitairement, en C, en shell, ou en haskell ? Quel vocabulaire emploies-tu pour discuter avec d'autres équipes, et mettre au point les tests du service global ?
— Encore une fois, tu pinailles. Il suffit que nous définissions explicitement les termes de Mike Cohn, et tout ira bien.
— Premièrement, félicitations. Tu dis que tu veux rendre les définitions explicites, et ça vaut le coup de s'y mettre. Les gens arrivent avec leur culture, et des définitions différentes pour les mêmes mots. Si c'est aussi simple, ça prendra peu de temps. Ensuite, comme ça, tu restes sur les trois termes de Mike Cohn?
— Exactement, le nombre magique.
— Souviens-toi du produit Spring, où vous classiez en test d'intégration tout ce qui n'était pas déjà unitaire ou de bout en bout. Tu sentais que vous ratiez des opportunités en essayant de rentrer au chausse-pied tous ces tests dans le framework commun. C'était lourd n'est-ce pas ?

Pluto regarda son bureau.
— Oh oui ça l'était. Il y eu quelques bagarres à ce sujet. Alors nommons quelques catégories dans notre contexte, et utilisons-les partout.
— Voilà. Et n'oublie pas de garder cette liste vivante. Maintenant, vous avez besoin de découvrir ce qu'est votre contexte. En avez-vous un seul ? Pour le département ? La technologie a-t-elle une influence ? Le métier ? La culture ?
— Tu veux dire que nous devrions avoir des jeux de catégories par service, par jeu de service, ou que nous devrions partager un vocabulaire avec les autres équipes ?
— Tout ça, rien de tout ça, je n'en sais rien. Prenez ce qui a du sens. Parlez-en. Rendez les chose explicites et pertinentes.
— Finalement, de la pyramide des tests, il ne reste que le triangle.

David s'assit dans le canapé et fixa Pluto.
— ...
— Quoi ? Les tests sont soit rapides et fiables, ou ils représentent la réalité, sont plus gros, et plus fragiles. N'est-ce pas ?
— Intéressant.
— Tu joues le psy ?
— Est-ce que je joue le psy ?
— Je ne te connaissais pas comme ça, David.
— Tu le dis toi-même. Les tests ont plusieurs propriété désirables, et tu veux toutes les maximiser. Entre autre, il y a
- la rapidité, pour faire tourner un maximum de tests,
- l'expressivité, du code et des diagnostiques,
- l'isolation, de l'environnement d'exécution et des fonctionnalités testées: quand un test plante, tu veux savoir pourquoi,
- la fiabilité, c'est à dire que tu ne veux pas que les tests clignotent. [Les tests qui embarquent le plus de choses sont les plus fragiles](https://testing.googleblog.com/2017/04/where-do-our-flaky-tests-come-from.html),
- la représentativité. Par exemple, un test est-il représentatif de la vraie vie s'il n'inclue pas la planification des scripts qui déplacent les fichiers d'entrée dans les répertoires d'entrée ? L'environnement de production est-il représentatif si tu utilises un flag de test dans les requêtes entrantes ?
- la couverture. Pense à l'explosion combinatoire de tous les cas aux limites de votre produit,
- et beaucoup d'autres
Tu vois bien que la plupart de ces propriétés entrent en conflit entre elles. Dans chaque contexte, vous trouverez des boîtes à outils qui vous offriront chacune un compromis raisonnable. Dans certains contextes, ces ensembles seront proprement ordonnés dans une belle pyramide. Dans d'autres contextes, vous réussirez à maximiser la plupart des propriétés dans une seule catégorie. Les propriétés ne s'opposent pas dans un gradient linéaire. Ca dépend.
— C'est plus des bulles multi-dimensionnelles qu'une pyramide quoi.
— toussenerdtousse
— Mais "[les tests montrent la présence de bugs, pas leur absence](http://homepages.cs.ncl.ac.uk/brian.randell/NATO/nato1969.PDF)", n'est-ce pas ?
— Je n'ai jamais dit le contraire. J'ai bien parlé de compromis raisonnables. Vous identifierez les bonnes bulles avec votre sensibilité. C'est une question de confiance, c'est très subjectif. Oh et bien sûr, nous parlons bien d'automatisation, pas de [tests à proprement parler](https://www.developsense.com/blog/2009/08/testing-vs-checking/).
— Finalement, il ne reste plus rien de la pyramide. Michael Knight bat Mike Cohn.
— Pas du tout, tu es dingue! Je te l'ai dit, la métaphore est géniale. Quand je l'ai découverte, ça a été une épiphanie. On parle d'un contexte précis, ici, pas d'une manière de penser générique. La pyramide [n'est qu'un modèle, et est donc fausse](https://en.wikipedia.org/wiki/All_models_are_wrong), c'est tout. Ce modèle est particulièrement simpliste, et résiste difficilement au contact avec le terrain, mais il est extrêmement utile en tant qu'exercice de pensée.

Pluto se pencha sur son fauteuil, se massant le nez et s'étirant les jambes.
— Et voilà, tu l'as encore fait, il va falloir que je retourne discuter avec l'équipe.
Quand il rouvrit les yeux, David Hasselhoff était à nouveau sur l'affiche.
— Il faut vraiment que je dorme plus.

_Crédit image Mountain Goat Software et Mike Cohn_
