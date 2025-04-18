---
title: "Exercices, série 8"
permalink: semantique/exercices/Ex8_Composition/
layout: archive
published: true
hidden: true
---

## Composition sémantique

Actifs de 1996 à 2001, les *2Be3* étaient et resteront pour toujours le plus connu des boys-band français, ayant connu une carrière brève mais fulgurante comprenant trois albums studio vendus à plus de cinq millions d'exemplaires. Leurs [chorégraphies](https://www.youtube.com/watch?v=3c7DDnjrXFw) comprenant moult figures de breakdance (backflip, [airflare](https://www.youtube.com/watch?v=1fxOuGQcEsI)) et autres chemises ouvertes sur des abdominaux ont fait rêver des millers d'adolescent.e.s de cette génération.

Considérons donc le modèle $M_{2Be3}$ suivant:

$$
D_{M_{2Be3}} = \{ \text{Adel, Filip, Frank}
\}
$$


$$
M_{2Be3} =
\left[ \begin{aligned}
  &a \rightarrow \text{Adel} \\
  &fi \rightarrow \text{Filip} \\
  &fr \rightarrow \text{Frank} \\
  &chanter.avec \rightarrow \{ \langle a, fi \rangle, \langle a, fr \rangle, \langle fi, a \rangle, \langle fi, fr \rangle, \langle fr, a \rangle, \langle fr, fi \rangle \} \\
  &danser.avec \rightarrow \{ \langle a, fr \rangle, \langle fr, a \rangle, \langle fi, a \rangle \} \\
  &avoir.des.abdos \rightarrow \{ a, fr, fi \} \\
  &faire.un.backflip \rightarrow \{ fi \} \\
  &faire.un.airflare \rightarrow \{ a \} \\
\end{aligned} \right]
$$

*Notez que cette liste n'est pas exhaustive, et que certains prédicats ne sont pas définis explicitement dans $M_{2Be3}$; vous êtes donc libres de déterminer leur valeur.*

Calculez la dénotation des expressions suivantes dans $M_{2Be3}$.
Pour chaque expression, vous définirez d'abord les entrées lexicales nécessaires, en les définissant dans LL et en déterminant leur type. Vous appliquerez ensuite la lambda-conversion à chaque expression, déterminant ainsi la valeur de chaque expression composée, d'après ce modèle:

(1) $\llbracket \text{Frank chante avec Adel} \rrbracket^{M_{2Be3}}$ = 1 ssi $chante.avec(fr,a)$ dans $M_{2Be3}$

Entrées lexicales:

- $\llbracket \text{Frank} \rrbracket^{M_{2Be3}} = fr_{e}$  
- $\llbracket \text{Adel} \rrbracket^{M_{2Be3}} = a_{e}$  
- $\llbracket \text{chante avec} \rrbracket^{M_{2Be3}} = \lambda y. \lambda x. chanter.avec (x,y)_{\langle e, \langle e,t \rangle \rangle}$  

Composition:

1. $\llbracket \text{chante avec} \rrbracket^{M_{2Be3}}(\llbracket \text{Adel} \rrbracket^{M_{2Be3}}) = \[\lambda y. \lambda x. chanter.avec (x,y)\]\_{\langle e, \langle e,t \rangle \rangle}(a)\_{e} = \lambda x. chanter.avec(x,a)\_{\langle e,t \rangle}$
2. $\llbracket \text{chante avec Adel} \rrbracket^{M_{2Be3}}(\llbracket \text{Frank} \rrbracket^{M_{2Be3}}) = \[\lambda x. chanter.avec(x,a)\]\_{\langle e,t \rangle}(fr\_{e}) = chanter.avec(fr,a)\_{t}$

Dénotation:

(1) $\llbracket \text{Frank chante avec Adel} \rrbracket^{M_{2Be3}}$ = 1

---

1. Frank danse avec Filip.
2. Filip est le leader.  
   *$\equiv$ "Filip est leader"; dans cette position, l'article défini n'est pas interprété sémantiquement.*
4. Adel fait un airflare.
5. Frank n'est pas content.
1. Adel et Frank sont jaloux de Filip.
2. Filip, Adel et Frank ont des abdos.  
   *$\equiv$ "Filip et Adel et Frank ont des abdos"*
3. Filip chante et Frank danse avec Adel.
5. Adel et Frank ne font pas de backflip.

---

**Nouvelles entrées lexicales:**

$\llbracket \text{Neg} \rrbracket = \lambda P. \lambda x. \neg P(x)_{\langle \langle e,t \rangle, \langle e,t \rangle \rangle}$ 

$\llbracket \text{est, sont} \rrbracket = \lambda P. P_{\langle \langle e,t \rangle, \langle e,t \rangle \rangle}$  

*Une fonction d'identité sur des prédicats.*

$\llbracket \text{de} \rrbracket = \lambda x.x_{\langle e,e \rangle}$

*Une fonction d'identité sur des individus.*

$\llbracket \text{et} \rrbracket = \lambda p. \lambda q. p \land q_{\langle t, \langle t,t \rangle \rangle}$

*L'entrée standard de la conjonction. $p$ et $q$ sont des variables sur des propositions.*

$\llbracket \text{et}_{individus} \rrbracket = \lambda y. \lambda x. x \oplus y\_{\langle e, \langle e,e \rangle \rangle}$  

*Le symbole $\oplus$ est issu des travaux de Link (1983) sur la pluralité et désigne la pluralité formée par deux individus/atomes; ainsi, cette entrée prend deux individus de type $e$ et retourne un individu pluriel composé de ces deux individus, également de type $e$.*

$\llbracket \text{et}_{prédicats} \rrbracket = \lambda Q. \lambda P. \lambda x. P(x) \land Q(x)\_{\langle e,t \langle \langle e,t \rangle, \langle e,t \rangle \rangle \rangle}$  

*Cette entrée de* et *permet de conjoindre deux prédicats.*

---

**Références**

Link, Godehard (1983). "The logical analysis of plurals and mass terms: A lattice-theoretical approach". In Rainer Bäuerle, Christoph Schwarze, and Arnim von Stechow (eds.), *Meaning, Use and Interpretation of Language*, 302–323. Berlin: de Gruyter.
