---
title: "Exercices, série 6"
permalink: semantique/exercices/Ex6_Lambda1/
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

 1. $[\lambda x. x](a)$
 2. $[\lambda P. P](femme)$
 3. $[\lambda x. P(x)](a)$
 4. $[\lambda x. P(x)]$
 5. $[\lambda y. \lambda x. R(y,x)](a)$
 6. $[\lambda x. R(y,a)](b)$
 7. $[\lambda P. \exists x. P(x)](femme)$
 8. $[\lambda P. \forall x. P(x)](mortelle)$
 9. $\lambda x. \neg mortelle(x)$
 10. $[\lambda P. \lambda x. \neg P(x)](mortelle)$
 11. $[\lambda x. \neg mortelle(x)](a)$
 12. $[\lambda Q. \forall x. [femme(x) \rightarrow Q(x)]](mortelle)$
 13. $[\lambda P. \lambda Q. \forall x. [P(x) \rightarrow Q(x)]](femme)$
 14. $[\lambda P. \lambda Q. \forall x. [P(x) \rightarrow Q(x)]](femme)(mortelle)$
 15. $[\lambda x. P(x) \land Q(x)](a)$
 16. $[\lambda x. \lambda y. [R(y,a) \land Q(x)]](a)(b)$
 17. $[\lambda x. a] (b)$
 18. $[\lambda x. [P(x) \rightarrow \exists x. R(b,x)]](a)$
 19. $[\lambda Q. \forall x. [mortelle(x) \rightarrow Q(x)]](\lambda x. [mortelle(x)])$
 20. $[\lambda Q. \exists P. \forall x. [P(x) \rightarrow Q(x)]](mortelle)$
 21. $[\lambda P. \lambda x. \neg P(x)](\lambda x.mortelle(x))$
 22. $[\lambda P. \lambda x. P(x)](\lambda x.[\neg mortelle(x)])$
