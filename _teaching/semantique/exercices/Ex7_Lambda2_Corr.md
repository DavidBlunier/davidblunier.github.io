---
title: "Exercices série 7, corrigé"
permalink: semantique/exercices/Ex7_Lambda2_Corr/
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

1. $\lambda y. \lambda x. R(x,y): \langle e, \langle e,t \rangle$
2. $\[\lambda y. \lambda x. R(x,y)\](a): \langle e,t \rangle$
3. $\[\lambda x. R(x,a)\](b): t$
4. $R(a,b): t$
5. $\lambda x.\[P(x) \land Q(x)\]: \langle e,t \rangle$
6. $\[\lambda x.\[P(x) \land Q(x)\]\](a): t$
7. $\lambda P. P: \langle \langle e,t \rangle, \langle e,t \rangle \rangle$
8. $\lambda P. P(a): \langle \langle e,t \rangle, t \rangle$
9. $\exists x. P(x): t$
10. $\lambda P.\exists x. P(x): \langle \langle e,t \rangle, t \rangle$
11. $\[\lambda P.\exists x. P(x)\](femme): t$
12. $\exists x. femme(x): t$
13. $\lambda P.\forall x. P(x): \langle \langle e,t \rangle, t \rangle$
14. $\[\lambda P.\forall x. P(x)\](mortelle): t$
15. $\neg mortelle(x): t$
16. $\lambda x. \neg mortelle(x): \langle e,t \rangle$
17. $\lambda P \lambda x. \neg P(x): \langle \langle e,t \rangle, \langle e,t \rangle \rangle$
18. $\[\lambda P \lambda x. \neg P(x)\](mortelle): \langle e,t \rangle$
19. $\lambda x. \neg mortelle(a): \langle e,t \rangle$
20. $\[\lambda x. \neg mortelle(x)\](a): t$


II. Considérez les expressions suivantes:

1. $\[\lambda x. P(x)\](a) \equiv P(a)_{t}$
2. $\[\lambda x. P(x)(a)\]$: expression mal formée
3. $\[\lambda x. R(y,a)\]_{\langle e,t \rangle}$
4. $\[\lambda x. R(y,a)\](b) \equiv R(y,a)_{\langle e,t \rangle}$
5. $\[\lambda x. R(x,a)\](b) \equiv R(b,a)_{t}$
6. $\[\lambda x. \lambda y. R(x,y)\](b) \equiv \lambda y.R(b,y)_{\langle e,t \rangle}$
7. $\[\lambda x. \lambda y. R(x,y)\](b)(a) \equiv R(b,a)_{t}$
8. $\[\lambda x. \[ \lambda y. R(x,y)\](b)\](a) \equiv R(a,b)_{t}$
9. $\[\lambda X. \exists x. \[P(x) \land X(x)\]\](\lambda y. R(a,y)) \equiv \exists x. \[P(x) \land (\lambda y. R(a,y)(x))\] \equiv \exists x. \[P(x) \land R(a,x)\]_{t}$ (via lambda-conversion puis alpha-conversion de $y$ à $x$)
10. $\[\lambda X. \exists x. \[P(x) \land X(x)\]\](\lambda x. R(a,x)) \equiv \exists x. \[P(x) \land R(a,x)\]_{t}$
11. $\[\lambda X. \exists x. \[P(x) \land X(x)\]\](\lambda y. R(y,x)) \equiv \exists x. \[P(x) \land R(x,x)\]_{t}$
12. $\[\lambda X. \exists x. \[P(x) \land X(x)\]\](Q) \equiv \exists x. \[P(x) \land Q(x)\]_{t}$
13. $\[\lambda X. \exists x. \[P(x) \land X(x)\]\](X) \equiv \exists x. \[P(x) \land X(x)\]_{t}$
14. $\[\lambda X. \exists x. \[P(x) \land X(x)\](\lambda x. Q(x))\] \equiv \exists x. \[P(x) \land (\lambda x. Q(x))(x)\] \equiv \exists x. \[P(x) \land Q(x)\]_{t}$
15. $\[\lambda y. \lambda x. R(y,x)\](a) \equiv \lambda x. R(a,x)_{\langle e,t \rangle}$

Pour chacune des expressions ci-dessus, répondez aux questions suivantes:

1. S'agit-il d'une expression bien formée de LL? Si oui, quel est son type?
2. S'il s'agit d'une expression bien formée et lorsque cela est possible, donnez une version complètement réduite de la formule (via lambda-conversion); utilisez la règle d'alpha-conversion (i.e., renommez les variables quand cela est nécessaire), afin d'éviter toute capture de variable accidentelle.
