---
title: "Examen: logique propositionnelle, logique des prédicats - corrigé"
permalink: semantique/exercices/Examen_LProp_LPred_Corr/
layout: archive
published: true
hidden: true
---

Considérez les arguments suivants:

> 1. P1: Si les élèves étudient, ils réussissent l'examen.  
> P2: Les élèves ont réussi l'examen.  
> C: Les élèves ont étudié.
> 2. P1: Si tous les oiseaux ont des ailes, alors les pingouins volent.  
> P2: Les pingouins ne volent pas.  
> C: Tous les oiseaux n'ont pas d'ailes.

1. Pour chaque argument, déterminez si il s'agit d'un argument **valide** et/ou **fondé**.
2. Justifiez vos réponses en construisant les tables de vérité de chaque argument.

> Aide: pour ce faire, vous devez tout d'abord formaliser ces arguments en logique propositionnelle.

3. Traduisez les deux arguments en logique des prédicats.

## Corrigé

1. Structure du premier argument:

> P1: $p \rightarrow q$  
> P2: $q$  
> C: $\not \therefore p$

Cet argument n'est ni valide, ni fondé: il s'agit d'une fallacie (affirmation du conséquent), comme le montre la table de vérité suivante (1pt, si la réponse est congruente avec les résultats obtenus dans les tables de vérité):

> | $p$ | $q$ | $p \rightarrow q$ | $\[p \rightarrow q\] \land q$ | $\[\[p \rightarrow q\] \land q\]\] \rightarrow p$
> |---|---|---|---|---|
> | 1   | 1   | 1 | 1 | **1**
> | 0   | 1   | 1 | 1 | **0**
> | 1   | 0   | 0 | 0 | **1**
> | 0   | 0   | 1 | 0 | **1**

*(1 pt pour avoir posé les valeurs de $p$ et $q$ correctement, puis 1pt/colonne. Erreur de calcul: -0.25pt. Total: 4pt)*

Comme il existe au moins un modèle dans lequel l'implication matérielle des prémisses à la conclusion est fausse (le deuxième), l'argument n'est logiquement invalide.

Mais comme toujours, nos intuitions basées sur le langage naturel peuvent nous tromper: si la première prémisse est interprétée en LProp comme contenant un **biconditionnel** (ssi, si et seulement si) plutôt qu'une implication matérielle, alors l'argument devient valide, et nous pouvons en conclure que si les élèves ont réussi l'examen, alors ils ont nécessairement étudié.

> | $p$ | $q$ | $p \leftrightarrow q$ | $\[p \leftrightarrow q\] \land q$ | $\[\[p \leftrightarrow q\] \land q\]\] \rightarrow p$
> |---|---|---|---|---|
> | 1   | 1   | 1 | 1 | **1**
> | 0   | 1   | 0 | 0 | **1**
> | 1   | 0   | 0 | 0 | **1**
> | 0   | 0   | 1 | 0 | **1**

Cet argument se traduit en logique des prédicats de la façon suivante:

> P1: $\forall x. \[élève(x) \rightarrow \[étudie(x) \rightarrow réussir.examen(x)\]\]$  
> *également accepté:*  
> P1 $\forall x. \[\[élève(x) \land étudie(x)\] \rightarrow réussir.examen(x)\]$  
> 
> P2: $\forall x. \[élève(x) \rightarrow réussir.examen(x)\]$  
> 
> C: $\not \therefore \forall x. \[élève(x) \rightarrow étudie(x)\]$

> *Variante, plus précise:*  
> P1: $\exists y. \[examen(y) \land \forall x. \[élève(x) \rightarrow \[étudie(x) \rightarrow réussir(x,y)\]\]\]$  
> 
> P2: $\exists y. \[examen(y) \land \forall x. \[élève(x) \rightarrow réussir(x,y)\]\]$  
> 
> C: $\not \therefore \forall x. \[élève(x) \rightarrow étudie(x)\]$

> *NB: pour les deux variantes, il était également possible de transcrire P2 et C en utilisant un quantificateur existentiel:*  
> 
> P1: $\forall x. \[élève(x) \rightarrow \[étudie(x) \rightarrow réussir.examen(x)\]\]$  
>  
> P2: $\exists x. \[élève(x) \land réussir.examen(x)\]$  
> 
> C: $\not \therefore \exists x. \[élève(x) \land étudie(x)\]$

*(1 pt par formule correcte. Total: 3pt)*




1. Structure du second argument:

> P1: $p \rightarrow q$  
> P2: $\neg q$  
> C: $\therefore \neg p$

Cet argument est valide, mais infondé: dans notre monde, les pingouins sont des oiseaux et ont effectivement des ailes, mais ne volent pas. La première prémisse est donc fausse. Néanmoins, la conclusion découle logiquement des prémisses (il s'agit d'un *modus tollens*), ce qui suffit à en faire un argument valide (1pt pour la validité, 1pt pour la fondation, si la réponse est congruente avec les résultats obtenus dans les tables de vérité). Voici la table de vérité qui le prouve:

> | $p$ | $q$ | $p \rightarrow q$ | $\neg q$ | $\neg p$ | $\[p \rightarrow q\] \land \neg q$ | $\[\[p \rightarrow q\] \land \neg q\] \rightarrow \neg p$
> |---|---|---|---|---|---|---
> | 1   | 1   | 1 | 0 | 0 | 0 | **1**
> | 0   | 1   | 1 | 0 | 1 | 0 | **1**
> | 1   | 0   | 0 | 1 | 0 | 0 | **1**
> | 0   | 0   | 1 | 1 | 1 | 1 | **1**

L'argument est vrai dans tous les modèles, donc valide.

*(1 pt pour avoir posé les valeurs de $p$ et $q$ correctement, puis 1pt/colonne. Erreur de calcul: -0.25pt. Total: 6pt)*

Il se traduit en LPred ainsi:

> *Variante 1: portée étroite de la négation*  
> P1: $\forall x. \[oiseau(x) \land ailé(x)\] \rightarrow \[\forall y.\[pingouin(y) \rightarrow vole(y)\]\]$  
> 
> P2: $\forall x.\[pingouin(x) \rightarrow  \neg vole(x)\] \equiv$  
> $\neg \exists x. \[pingouin(x) \land vole(x)\]$  
> 
> C: $\therefore \forall x.\[oiseau(x) \rightarrow \neg ailé(x)\] \equiv$  
> $\neg \exists x.\[oiseau(x) \land ailé(x)\]$

Traduit de cette manière, la dernière ligne de l'argument signifie *aucun oiseau n'a d'ailes* (ce qui est faux). Comme la négation est ambiguë en français, la dernière ligne peut également être interprétée de la façon suivante, dans laquelle la négation prend une portée large sur le reste de la formule et qui se lit *pas tous les oiseaux ont des ailes* (ce qui est également faux: tous les membres de la famille *aves* ont des ailes, mais pas forcément fonctionnelles pour le vol):

> *Variante 2: portée large de la négation*  
> P1: $\forall x. \[oiseau(x) \rightarrow ailé(x)\] \rightarrow \[\forall y.\[pingouin(y) \rightarrow vole(y)\]\]$  
> 
> P2: $\forall x.\[pingouin(x) \rightarrow  \neg vole(x)\] \equiv$  
> $\neg \exists x. \[pingouin(x) \land vole(x)\]$  
> 
> C: $\therefore \neg \forall x.\[oiseau(x) \rightarrow ailé(x)\] \equiv$  
> $\exists x.\[oiseau(x) \land \neg ailé(x)\]$

*(1 pt par formule correcte. Total: 3pt)*

*Total des points: 19*
