---
title: "Exercices série 6, corrigé"
permalink: semantique/exercices/Ex6_Lambda1_Corr/
layout: archive
published: true
hidden: true
---

## Lambda-calcul, fondations

1. Lorsque cela est possible, appliquez la règle de lambda-conversion aux expressions suivantes:

> Rappel:
>
> - $x, y$ sont des variables d'individus  
> - $a, b$ sont des constantes d'individus  
> - $P, Q, X$ sont des variables de prédicats unaires (ne prenant qu'un argument)  
> - $R$ est une variable de prédicat binaire (prenant deux arguments)  
> - $femme$ et $mortelle$ sont des constantes de prédicats unaires.

 1. $\[\lambda x. x\](a) \equiv a$
 2. $\[\lambda P. P\](femme) \equiv femme$
 3. $\[\lambda x. P(x)\](a) \equiv P(a)$
 4. $\[\lambda x. P(x)\]$
 5. $\[\lambda y. \lambda x. R(y,x)\](a) \equiv \lambda x. R(a,x)$
 6. $\[\lambda x. R(y,a)\](b) \equiv R(b,a)$
 7. $\[\lambda P. \exists x. P(x)\](femme) \equiv \exists x. femme(x)$
 8. $\[\lambda P. \forall x. P(x)\](mortelle) \equiv \forall x. mortelle(x)$
 9. $\lambda x. \neg mortelle(x)$
 10. $\[\lambda P. \lambda x. \neg P(x)\](mortelle) \equiv \lambda x. \neg mortelle(x)$
 11. $\[\lambda x. \neg mortelle(x)\](a) \equiv \neg mortelle(a)$
 12. $\[\lambda Q. \forall x. \[femme(x) \rightarrow Q(x)\]\](mortelle) \equiv \forall x. \[femme(x) \rightarrow mortelle(x)\]$
 13. $\[\lambda P. \lambda Q. \forall x. \[P(x) \rightarrow Q(x)\]\](femme) \equiv \lambda Q. \forall x. \[femme(x) \rightarrow Q(x)\]$
 14. $\[\lambda P. \lambda Q. \forall x. \[P(x) \rightarrow Q(x)\]\](femme)(mortelle) \equiv \forall x. \[femme(x) \rightarrow mortelle(x)\]$
 15. $\[\lambda x. P(x) \land Q(x)\](a) \equiv P(a) \land Q(a)$
 16. $\[\lambda x. \lambda y. \[R(y,a) \land Q(x)\]\](a)(b) \equiv R(b,a) \land Q(a)$
 17. $\[\lambda x. a\] (b)$
 18. $\[\lambda x. \[P(x) \rightarrow \exists x. R(b,x)\]\](a) \equiv P(a) \rightarrow \exists x.R(b,x)$
 19. $\[\lambda Q. \forall x. \[mortelle(x) \rightarrow Q(x)\]\](\lambda x. \[mortelle(x)\]) \equiv \forall x. \[mortelle(x) \rightarrow mortelle(x)\]$
 20. $\[\lambda Q. \exists P. \forall x. \[P(x) \rightarrow Q(x)\]\](mortelle) \equiv \exists P. \forall x. \[P(x) \rightarrow mortelle(x)\]$
 21. $\[\lambda P. \lambda x. \neg P(x)\](\lambda x.mortelle(x)) \equiv \lambda x. \neg mortelle(x)$
 22. $\[\lambda P. \lambda x. P(x)\](\lambda x.\[\neg mortelle(x)\]) \equiv \lambda x. \neg mortelle(x)$
