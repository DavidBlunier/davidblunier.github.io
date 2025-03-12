---
title: "Exercices série 2, Corrigé"
permalink: semantique/exercices/Ex2_Corr/
layout: archive
mathjax: true
published: true
hidden: true
---

## Exercices série 2: logique propositionnelle

> Rappel: *Modus Ponens*  
> $p \rightarrow q$  
> $p$  
> $\therefore$ q

1. Construisez un argument d'après le *modus ponens*.

> a. Si une personne participe, alors elle réussit.  
> b. Les étudiant.e.s participent.  
> c. $\therefore$ Les étudiant.e.s réussissent.

> Rappel: Affirmation du conséquent (fallacie)  
> $p \rightarrow q$  
> $q$  
> $\not \therefore$ p

2. Construisez un argument fallacieux employant l'affirmation du conséquent.

> a. Si une personne participe, alors elle réussit.  
> b. Les étudiant.e.s ont réussi.  
> c. $\not \therefore$ Les étudiant.e.s ont participé.

3. Voici deux autres types d'arguments. D'après vous, lequel est un type d'argument valide? Lequel est une fallacie? Expliquez pourquoi.

   1. a. S'il a plu hier au soir, alors la    pelouse est mouillée.  
      b. La pelouse est sèche.  
      c. Donc, il n'a pas plus hier au soir.

    > Argument valide (*modus tollens*)
   
   2. a. S'il a plu hier au soir, alors la    pelouse est mouillée.  
      b. Il n'a pas plu hier au soir.  
      c. Donc, la pelouse n'est pas mouillée.

     > Fallacie (négation de l'antécédent)

4. Donnez la table de vérité de la disjonction **exclusive**, également appelée XOR.

> | $p$ | $q$ | $p \veebar q$ |  
> |---|---|---|  
> | 1   | 1   | 0   |  
> | 1   | 0   | 1   |
> | 0   | 1   | 1   |
> | 0   | 0   | 0   |

5. Donnez la table de vérité de $\neg [p \land q]$.

> | $p$ | $q$ | $p \land q$ |   $\neg [p \land q]$ |
> |---|---|---|---| 
> | 1   | 1   | 1   | 0
> | 1   | 0   | 0   | 1
> | 0   | 1   | 0   | 1
> | 0   | 0   | 0   | 1

> **Définition: équivalence ($\equiv$)**  
> Deux formules sont dites **équivalentes** lorsqu'elles ont les mêmes conditions de vérité (i.e., qu'elles sont vraies dans les exactement les mêmes modèles).

6. Une des lois de De Morgan est l'équivalence suivante:

$$\neg [p \wedge q]\equiv [\neg p \lor \neg q]$$

En utilisant la table de vérité que vous venez d'établir, prouvez cette équivalence.

> |$\neg [p \land q]$ | $\neg p$ | $\neg q$ | $[\neg p \lor \neg q]$   |
> |---|---|---|---| 
> | 0   | 0   | 0   | 0
> | 1   | 0   | 1   | 1
> | 1   | 1   | 0   | 1
> | 1   | 1   | 1   | 1

7. Une autre loi de De Morgan est l'équivalence suivante: $\neg [p \lor q]\equiv [\neg p \wedge \neg q]$. Construisez la table de vérité nécessaire à prouver cette équivalence.

> |$p$ | $q$ | $\neg p$ | $\neg q$ | $p \lor q$ |  |
> |---|---|---|---|---|---|
> | 1 | 1 | 0 | 0 | 1
> | 0 | 0 | 1 | 1 | 0
> | 1 | 0 | 0 | 1 | 1
> | 0 | 1 | 1 | 0 | 1


> | $[\neg p \land \neg q]$ | $\neg [p \lor q]$ |
> |---|---|
> | 0   | 0
> | 1   | 1
> | 0   | 0
> | 0   | 0
