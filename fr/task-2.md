<div class="centered">
<img alt="démo de la sommation d'un tableau" src="http://s5.postimg.org/ixq2y0nnb/sum_in_loop.gif"/>
</div>

Maintenant notre but sera d'apprendre les **boucles** - c'est à dire des actions répétées.
Nous trouverons la somme de plusieurs nombres (plus de deux). Il sera utile de faire ceci en boucle.
Tel qu'illustré ci-dessus - vous pouvez créez une variable `sum` et lui additionner chaque valeur de la liste.
Peut-être qu'une [boucle "for"](https://fr.wikipedia.org/wiki/Boucle_for) fera l'affaire car le nombre de valeurs
est préalablement connu.

Si vous avez de la difficulté, essayez le problème [Sums In Loop](./sums-in-loop) d'abord - il est possiblement plus simple.

**Input data** (Données fournies) ont le format suivant:

- la 1ère ligne contient `N` - le nombre de valeur à additionner;
- la 2ième ligne contient les `N` valeurs en question.

**Answer** (Réponse) devrait contenir une seule valeur - la somme des `N` valeurs.

Exemple:

	input data:
	8
	10 20 30 40 5 6 7 8
	
	answer:
	126

**Note** puisqu'il y a plusieurs dizaines de nombres, vous ne devriez pas les copier manuellement dans votre programme.
À la place, créez votre programme pour qu'il lise de "standard input" (ou vous pouvez les copiers tous d'un seul coup).
Notez que si vous exécutez le code directement sur notre serveur, les données du problème seront copiées vers "standard input"
automatiquement afin de vous simplifier la tâche.
