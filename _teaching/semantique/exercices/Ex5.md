---
title: "Exercices, série 5"
permalink: semantique/exercices/Ex5/
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
   1. $\text{\llbracket} o \text{\rrbracket}^{M_{1}}$
   2. $\llbracket r \rrbracket^{M_{1}}$
   3. $\llbracket répare(db,o) \rrbracket^{M_{1}}$
   4. $\llbracket interfère.avec(db, o) \rrbracket^{M_{1}}$
   5. $\llbracket énèrve(o, r) \rrbracket^{M_{1}}$

2. Qu'est ce que $g_{1}(y)$?
3. Qu'est-ce que $\llbracket x \rrbracket^{M_{1}, g_{1}}$?
4. Qu'est ce que $g_{1}[x \mapsto \text{le réparateur}](y)$?
5. Qu'est ce que $g_{1}[x \mapsto \text{le réparateur}](x)$?
6. Qu'est-ce que $\llbracket x \rrbracket^{M_{1}, g_{2}}$?
7. Qu'est-ce que $\llbracket z \rrbracket^{M_{1}, g_{2}}$?

8. Calculez la dénotation des expressions suivantes:

   1. $\llbracket répare(z,y) \rrbracket^{M_{1}, g_{1}}$
   2. $\llbracket en.retard(x) \rrbracket^{M_{1}, g_{1}}$
   3.  $\llbracket répare(z,y) \rrbracket^{M_{1}, g_{2}}$
   4.  $\llbracket interfère.avec(z,y) \rrbracket^{M_{1}, g_{2}}$
   5.  $\llbracket interfere.avec(x,y) \rrbracket^{M_{1}, g_{1}}$
   6.  $\llbracket énerve(x,db) \rrbracket^{M_{1}, g_{2}}$
   7.  $\llbracket répare(r,y) \rrbracket^{M_{1}, g_{2}}$

9. En considérant les règles sémantiques de quantification (existentielle et universelle), calculez la dénotation des expressions suivantes dans $M_{1}$:

> **Règle d'interprétation sémantique: quantification existentielle**
> $\llbracket \exists x. \phi \rrbracket^{M, g} = 1$ ssi il existe un individu $k \in D$ tel que $\llbracket \phi \rrbracket^{M, g[x \mapsto k]} = 1$.

> **Règle d'interprétation sémantique: quantification universelle**
> $\llbracket \forall \upsilon. \phi \rrbracket^{M, g} = 1$ ssi pour tous les individus $k \in D$, $\llbracket \phi \rrbracket^{M, g[\upsilon \mapsto k]} = 1$.

1. $\llbracket \exists x \exists y. répare(x,y) \rrbracket^{M_{1}, g}$
2. $\llbracket \exists x. en.retard(x) \rrbracket^{M_{1}, g}$
3. $\llbracket \exists x. interfere.avec(x,db) \rrbracket^{M_{1}, g}$
4. $\llbracket \forall x. en.retard(x) \rrbracket^{M_{1}, g}$
5. $\llbracket \forall x. énerve(x,db) \rrbracket^{M_{1}, g}$

> **Attention:** souvenez-vous qu'une variable liée par un quantificateur a la même valeur quelle que soit la fonction d'assignation $g$!
