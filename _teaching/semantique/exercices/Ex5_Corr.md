---
title: "Exercices, série 5: corrigé"
permalink: semantique/exercices/Ex5_Corr/
layout: archive
published: true
hidden: true
---

## Fonctions d'interprétation et d'assignation

Considérez le modèle $M_{1}$, dans lequel l'ensemble des individus $D_{M_{1}}$ sont les suivants:

$$
D_{M_{1}} = \{ \text{David Blunier, l'ordinateur de l'amphi Varda, le réparateur}
\}
$$

$$
M_{1} =
\left[ \begin{aligned}
  &db \rightarrow \text{David Blunier} \\
  &o \rightarrow \text{l'ordinateur} \\
  &r \rightarrow \text{le réparateur} \\
  &interfère.avec \rightarrow \{ \langle db, o \rangle, \langle o, db \rangle \} \\
  &énerve \rightarrow \{ \langle o, db \rangle \} \\
  &répare \rightarrow \{ \langle r, o \rangle, \langle db, o \rangle \} \\
  &en.retard \rightarrow \{ db, r \} \\
\end{aligned} \right]
$$

Ajoutons à $M_{1}$ les fonctions d'assignation $g_{1}$ et $g_{2}$ suivantes:

$$
g_{1} =
\left[ \begin{aligned}
  &x \mapsto \text{David Blunier} \\
  &y \mapsto \text{l'ordinateur} \\
  &z \mapsto \text{le réparateur} \\
\end{aligned} \right]

g_{2} =
\left[ \begin{aligned}
  &x \mapsto \text{l'ordinateur} \\
  &y \mapsto \text{David Blunier} \\
  &z \mapsto \text{David Blunier} \\
\end{aligned} \right]
$$

1. Quelle est la dénotation les objets suivants dans $M_{1}$?
   1. $\llbracket o \rrbracket^{M_{1}}$ = l'ordinateur
   2. $\llbracket r \rrbracket^{M_{1}}$ = le réparateur
   3. $\llbracket répare(db,o) \rrbracket^{M_{1}}$ = 1
   4. $\llbracket interfère.avec(db, o) \rrbracket^{M_{1}}$ = 1
   5. $\llbracket énèrve(o, r) \rrbracket^{M_{1}}$ = 0

2. Qu'est ce que $g_{1}(y)$?  
   l'ordinateur
3. Qu'est-ce que $\llbracket x \rrbracket^{M_{1}, g{_{1}}[y \mapsto r]}$?  
   David Blunier
4. Qu'est ce que $g_{1}\[x \mapsto r\](y)$?  
   l'ordinateur
5. Qu'est ce que $g_{1}\[x \mapsto r\](x)$?  
   le réparateur
6. Qu'est-ce que $\llbracket x \rrbracket^{M_{1}, g_{2}}$?  
   l'ordinateur
7. Qu'est-ce que $\llbracket z \rrbracket^{M_{1}, g{_{2}}[z \mapsto o]}$?  
   l'ordinateur

8. Calculez la dénotation des expressions suivantes:
   1. $\llbracket répare(z,y) \rrbracket^{M_{1}, g_{1}}$ = 1
   2. $\llbracket en.retard(x) \rrbracket^{M_{1}, g_{1}}$ = 1
   3.  $\llbracket répare(z,y) \rrbracket^{M_{1}, g_{2}}$ = 0
   4.  $\llbracket interfère.avec(z,y) \rrbracket^{M_{1}, g_{2}}$ = 0
   5.  $\llbracket interfere.avec(x,y) \rrbracket^{M_{1}, g_{1}[y \mapsto r]}$ = 0
   6.  $\llbracket énerve(x,db) \rrbracket^{M_{1}, g_{2}}$ = 1
   7.  $\llbracket répare(r,y) \rrbracket^{M_{1}, g{_{2}}[y \mapsto o]}$ = 1

9.  En considérant les règles sémantiques de quantification (existentielle et universelle), calculez la dénotation des expressions suivantes dans $M_{1}$:

> **Règle d'interprétation sémantique: quantification existentielle**
> $\llbracket \exists x. \phi \rrbracket^{M, g} = 1$ ssi il existe un individu $k \in D$ tel que $\llbracket \phi \rrbracket^{M, g[x \mapsto k]} = 1$.

> **Règle d'interprétation sémantique: quantification universelle**
> $\llbracket \forall u. \phi \rrbracket^{M, g} = 1$ ssi pour tous les individus $k \in D$, $\llbracket \phi \rrbracket^{M, g[u \mapsto k]} = 1$.

1. $\llbracket \exists x \exists y. répare(x,y) \rrbracket^{M_{1}, g}$ = 1
2. $\llbracket \exists x. en.retard(x) \rrbracket^{M_{1}, g}$ = 1
3. $\llbracket \exists x. interfere.avec(x,db) \rrbracket^{M_{1}, g}$ = 1
4. $\llbracket \forall x. en.retard(x) \rrbracket^{M_{1}, g}$ = 0
5. $\llbracket \forall x. énerve(x,db) \rrbracket^{M_{1}, g}$ = 0

> **Attention:** souvenez-vous qu'une variable liée par un quantificateur a la même valeur quelle que soit la fonction d'assignation $g$!
