## Exercices série 3

## Logique propositionnelle, implication

1. Prouvez l'équivalence suivante avec une table de vérité: [$p \rightarrow q] \equiv [\neg p \lor q]$.

> | $p$ | $q$ | $p \rightarrow q$ | $\neg p$ | $[\neg p \lor q]$ |
> |---|---|---|---|---|
> | 1   | 1   | 1   | 0 | 1
> | 0   | 1   | 1   | 1 | 1
> | 1   | 0   | 0   | 0 | 0
> | 0   | 0   | 1   | 1 | 1


2. Les tables de vérité nous permettent de déterminer si un argument est valide ou non: ce sera le cas ssi **la conclusion est vraie dans tous les cas où les prémisses sont vraies également**. Construisez une table de vérité prouvant la validité du *Modus Tollens*.

> Rappel: *Modus Tollens*  
> $p \rightarrow q$  
> $\neg q$  
> $\therefore \neg p$

> | $p$ | $q$ | $p \rightarrow q$
> |---|---|---|
> | 1   | 1   | 1
> | 0   | 1   | 1
> | 1   | 0   | 0
> | **0**   | **0**   | **1**
>
> Le seul modèle dans lequel i) **l'implication matérielle est vraie** et ii) **$q$ est faux** correspond à celui de la dernière ligne, qui implique nécessairement que $p$ est faux également.

1. De la même manière, prouvez à l'aide d'une table de vérité que la **négation de l'antécédent** est une fallacie (un argument invalide).

> Rappel: négation de l'antécédent  
> $p \rightarrow q$  
> $\neg p$  
> $\not \therefore \neg q$

> | $p$ | $q$ | $p \rightarrow q$
> |---|---|---|
> | 1  | 1   | 1
> | **0**  | **1**   | **1**
> | 1  | 0   | 0
> | **0**  | **0**   | **1**
>
> Contrairement à la situation correspondant au *modus tollens*, on peut trouver deux situations dans lesquelles l'implication matérielle est vraie et $p$ est fausse; par conséquent, nous ne pouvons pas conclure logiquement $\neg q$ à partir de $\neg p$. En d'autres termes, il s'agit d'une fallacie parce que la vérité de la conclusion n'est **pas** garantie par la vérité des prémisses.

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
>
> Il s'agit d'une tautologie (la formule est vraie dans tous les modèles).

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
>
> Cette formule n'est ni une tautologie, ni une contradiction; c'est une **formule contingente**.