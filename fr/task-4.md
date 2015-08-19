<div class="text-center">
	<img src="http://s5.postimg.org/j3mtrsuk7/min_of_two.gif" alt="Animation: Choisir le minimum"/>
</div>

La plupart des programmes doivent pouvoir effectuer des choix afin de prendre des décisions.
Nous allons maintenant voir comment programmer avec des conditions.

Ceci est habituellement accompli avec une instruction similaire à `if ... then ... else` (SI ... ALORS ... SINON) 
qui ressemble généralement à ceci:

    IF une_condition THEN
        faire_quelque_chose
    ELSE
        faire_autre_chose
    ENDIF

Tout dépendant de votre langage de programmation, la syntaxe peut différer et la portion `else` est presque
toujours optionnelle.

Plus de détails sont donnés sur Wikipédia: [Conditional statements][cond].

[cond]: http://en.wikipedia.org/wiki/Conditional_(computer_programming)

De deux nombres, choisissez celui avec la valeur minimale. Voici plusieurs paires de nombre pour des tests approfondis.

**Input data** contient le nombre de cas à tester sur la première ligne.  
Les lignes suivantes contiennent les paires de nombre à tester.  
Pour la réponse (**Answer**) indiquez le minimum de chaque ligne avec des espaces comme séparateur.

    data:
    3
    5 3
    2 8
    100 15
    
    answer:
    3 2 15
