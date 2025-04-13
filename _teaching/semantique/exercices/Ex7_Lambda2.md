---
title: "Exercices série 7"
permalink: semantique/exercices/Ex7_Lambda2/
layout: archive
published: true
hidden: true
---

## Lambda-calcul, suite


I. Identifiez le type des expressions suivantes:

> *Rappel*  
> $e$ est un type;  
> $t$ est un type;  
> Si $\sigma$ est un type et $\tau$ est un type, alors $\langle \sigma, \tau \rangle$ est un type;  
> Rien d'autre n'est un type.

> *Rappel:*  
> $x, y$ sont des variables d'individus  
> $a, b$ sont des constantes d'individus  
> $P, Q, X$ sont des variables de prédicats unaires (ne prenant qu'un argument)  
> $R$ est une variable de prédicat binaire (prenant deux arguments)  
> *femme* et *mortelle* sont des constantes de prédicats de type $\langle e, t \rangle$.

1. $\lambda y. \lambda x. R(x,y)$
2. $\[\lambda y. \lambda x. R(x,y)\](a)$
3. $\[\lambda x. R(x,a)\](b)$
4. $R(a,b)$
5. $\lambda x.\[P(x) \land Q(x)\]$
6. $\[\lambda x.\[P(x) \land Q(x)\]\](a)$
7. $\lambda P. P$
8. $\lambda P. P(a)$
9. $\exists x. P(x)$
10. $\lambda P.\exists x. P(x)$
11. $\[\lambda P.\exists x. P(x)\](femme)$
12. $\exists x. femme(x)$
13. $\lambda P.\forall x. P(x)$
14. $\[\lambda P.\forall x. P(x)\](mortelle)$
15. $\neg mortelle(x)$
16. $\lambda x. \neg mortelle(x)$
17. $\lambda P \lambda x. \neg P(x)$
18. $\[\lambda P \lambda x. \neg P(x)\](mortelle)$
19. $\lambda x. \neg mortelle(a)$
20. $\[\lambda x. \neg mortelle(x)\](a)$


II. Considérez les expressions suivantes:

1. $\[\lambda x. P(x)\](a)$
2. $\[\lambda x. P(x)(a)\]$
3. $\[\lambda x. R(y,a)\]$
4. $\[\lambda x. R(y,a)\](b)$
5. $\[\lambda x. R(x,a)\](b)$
6. $\[\lambda x. \lambda y. R(x,y)\](b)$
7. $\[\lambda x. \lambda y. R(x,y)\](b)(a)$
8. $\[\lambda x. \[ \lambda y. R(x,y)\](b)\](a)$
9. $\[\lambda X. \exists x. \[P(x) \land X(x)\]\](\lambda y. R(a,y))$
10. $\[\lambda X. \exists x. \[P(x) \land X(x)\]\](\lambda x. R(a,x))$
11. $\[\lambda X. \exists x. \[P(x) \land X(x)\]\](\lambda y. R(y,x))$
12. $\[\lambda X. \exists x. \[P(x) \land X(x)\]\](Q)$
13. $\[\lambda X. \exists x. \[P(x) \land X(x)\]\](X)$
14. $\[\lambda X. \exists x. \[P(x) \land X(x)\](\lambda x. Q(x))\]$
15. $\[\lambda y. \lambda x. R(y,x)\](a)$

Pour chacune des expressions ci-dessus, répondez aux questions suivantes:

1. S'agit-il d'une expression bien formée de LL? Si oui, quel est son type?
2. S'il s'agit d'une expression bien formée et lorsque cela est possible, donnez une version complètement réduite de la formule (via lambda-conversion); utilisez la règle d'alpha-conversion (i.e., renommez les variables quand cela est nécessaire), afin d'éviter toute capture de variable accidentelle.
