---
title: "Exercices série 3 (suite), Corrigé"
permalink: semantique/exercices/Ex3_Corr/
layout: archive
mathjax: true
published: true
hidden: true
---

## Logique propositionnelle (suite)

1. Prouvez l'équivalence suivante avec une table de vérité: [$p \rightarrow q] \equiv [\neg p \lor q]$.

> | $p$ | $q$ | $p \rightarrow q$ | $\neg p$ | $[\neg p \lor q]$ |
> |---|---|---|---|---|
> | 1   | 1   | **1**   | 0 | **1**
> | 0   | 1   | **1**   | 1 | **1**
> | 1   | 0   | **0**   | 0 | **0**
> | 0   | 0   | **1**   | 1 | **1**


2. Les tables de vérité nous permettent de déterminer si un argument est valide ou non: ce sera le cas ssi **l'argument est vrai dans tous les modèles**. Construisez une table de vérité prouvant la validité du *Modus Tollens*.

> Rappel: *Modus Tollens*  
> P1: $p \rightarrow q$  
> P2: $\neg q$  
> C: $\therefore \neg p$

Afin de déterminer si le *modus tollens* est un type d'argument valide (i.e., vrai dans tous les modèles possibles), nous devons d'abord **déterminer la valeur de vérité des prémisses et de la conclusion prises séparément**.

> | $p$ | $q$ | $p \rightarrow q$ | $\neg q$ | $\neg p$
> |---|---|---|---|---|
> | 1   | 1   | 1 | 0 | 0
> | 0   | 1   | 1 | 0 | 1
> | 1   | 0   | 0 | 1 | 0
> | 0   | 0   | 1 | 1 | 1

Puis, nous devons déterminer si **l'implication matérielle nous permettant de passer des prémisses à la conclusion est vraie dans tous les modèles**. Pour ce faire, nous devons calculer la valeur de vérité de l'argument **en entier**, c'est-à-dire la calculer la valeur de vérité de l'implication matérielle composée de **la conjonction des deux prémisses** (antécédent) et de la **conclusion** (conséquent). En langage semi-formel:

> $[[P1] \land [P2]] \rightarrow C$

Ce qui nous donne la table de vérité suivante:

> | $[[p \rightarrow q] \land \neg q]$ | $\neg p$ | $[[[p \rightarrow q] \land \neg q] \rightarrow \neg p]$
> |---|---|---|
> | 0 | 0 | **1**
> | 0 | 1 | **1**
> | 0 | 0 | **1**
> | 1 | 1 | **1**

Comme le montre la dernière colonne, la valeur de l'implication matérielle partant de la conjonction des deux prémisses P1 et P2 à la conclusion C est **vraie dans tous les modèles**; la conclusion découle donc nécessairement des prémisses, le *modus tollens* est donc une forme d'argument logiquement valide.

1. De la même manière, prouvez à l'aide d'une table de vérité que la **négation de l'antécédent** est une fallacie (un argument invalide).

> Rappel: négation de l'antécédent  
> P1: $p \rightarrow q$  
> P2: $\neg p$  
> C: $\not \therefore \neg q$

Nous suivons ici la même démarche que dans l'exercice précédent; afin de déterminer la validité ou l'invalidité logique d'un argument, nous devons établir sa table de vérité. Si l'argument est **faux dans au moins un modèle**, alors l'argument est invalide - il s'agit d'une fallacie.

Nous commençons par calculer la valeur de vérité des prémisses et de la conclusion séparément:

> | $p$ | $q$ | $p \rightarrow q$ | $\neg p$ | $\neg q$
> |---|---|---|---|---|
> | 1   | 1   | 1 | 0 | 0
> | 0   | 1   | 1 | 1 | 0
> | 1   | 0   | 0 | 0 | 1
> | 0   | 0   | 1 | 1 | 1

Puis nous calculons

> $[[P1] \land [P2]] \rightarrow C$

Ce qui nous donne la TV suivante:

> | $[[p \rightarrow q] \land \neg p]$ | $\neg q$ | $[[[p \rightarrow q] \land \neg p] \rightarrow \neg q]$
> |---|---|---|
> | 0 | 0 | **1**
> | 1 | 0 | **0**
> | 0 | 1 | **1**
> | 1 | 1 | **1**

Comme le montre la dernière colonne, **l'implication nous permettant de passer des prémisses à la conclusion est fausse dans au moins un modèle (le deuxième)**; l'argument est donc logiquement invalide, la négation de l'antécédent est bien une fallacie.

3. À l'aide de tables de vérité, prouvez que les formules suivantes sont équivalentes:  
   1. $[p \rightarrow q] \equiv [\neg q \rightarrow \neg p]$
   2. $[p \rightarrow p] \equiv [p \lor \neg p]$

> 1. $[p \rightarrow q] \equiv [\neg q \rightarrow \neg p]$
> 
> | $p$ | $q$ | $p \rightarrow q$ | $\neg p$ | $\neg q$ | $[\neg q \rightarrow \neg p]$
> |---|---|---|---|---|---|
> | 1  | 1   | 1 | 0 | 0 | 1
> | 0  | 1   | 1 | 1 | 0 | 1
> | 1  | 0   | 0 | 0 | 1 | 0
> | 0  | 0   | 1 | 1 | 1 | 1
>
> 2. $[p \rightarrow p] \equiv [p \lor \neg p]$
>
> | $p$ | $\neg p$ | $p \rightarrow p$ | $p \lor \neg p$
> |---|---|---|---|
> | 1 | 0 | 1 | 1
> | 0 | 1 | 1 | 1

1. Lesquelles des formules suivantes sont des tautologies? Des contradictions?
   1. $[[p \rightarrow q] \lor [q \rightarrow p]]$

> | $p$ | $q$ | $p \rightarrow q$ | $q \rightarrow p$ | $[[p \rightarrow q] \lor [q \rightarrow p]]$
> |---|---|---|---|---
> | 1  | 1   | 1 | 1 | 1
> | 0  | 1   | 1 | 0 | 1
> | 1  | 0   | 0 | 1 | 1
> | 0  | 0   | 1 | 1 | 1

Il s'agit d'une tautologie (la formule est vraie dans tous les modèles).

   2. $[[p \rightarrow q] \leftrightarrow [\neg q \lor \neg p]]$

> | $p$ | $q$ | $p \rightarrow q$ | $\neg p$ | $\neg q$ | $[\neg q \lor \neg p]$ |
> |---|---|---|---|---|---|
> | 1  | 1   | 1 | 0 | 0 | 0
> | 0  | 1   | 1 | 1 | 0 | 1
> | 1  | 0   | 0 | 0 | 1 | 1
> | 0  | 0   | 1 | 1 | 1 | 1
>
> | $[[p \rightarrow q] \leftrightarrow [\neg q \lor \neg p]]$ |
> |---
> 0
> 1
> 0
> 1

Cette formule n'est ni une tautologie, ni une contradiction; c'est une **formule contingente**.
