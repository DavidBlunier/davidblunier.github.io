---
title: "Exercices série 8, corrigé"
permalink: semantique/exercices/Ex8\_Composition\_Corr/
layout: archive
published: true
hidden: true
---

## Composition sémantique

Actifs de 1996 à 2001, les *2Be3* étaient et resteront pour toujours le plus connu des boys-band français, ayant connu une carrière brève mais fulgurante comprenant trois albums studio vendus à plus de cinq millions d'exemplaires. Leurs [chorégraphies](https://www.youtube.com/watch?v=3c7DDnjrXFw) comprenant moult figures de breakdance (backflip, [airflare](https://www.youtube.com/watch?v=1fxOuGQcEsI)) et autres chemises ouvertes sur des abdominaux ont fait rêver des millers d'adolescent.e.s de cette génération.

Considérons donc le modèle $M\_{2Be3}$ suivant:

$$
D\_{M\_{2Be3}} = \{ \text{Adel, Filip, Frank}
\}
$$


$$
M\_{2Be3} =
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

*Notez que cette liste n'est pas exhaustive, et que certains prédicats ne sont pas définis explicitement dans $M\_{2Be3}$; vous êtes donc libres de déterminer leur valeur.*

Calculez la dénotation des expressions suivantes dans $M\_{2Be3}$.
Pour chaque expression, vous définirez d'abord les entrées lexicales nécessaires, en les définissant dans LL et en déterminant leur type. Vous appliquerez ensuite la lambda-conversion à chaque expression, déterminant ainsi la valeur de chaque expression composée, d'après ce modèle:

(1) $\llbracket \text{Frank chante avec Adel} \rrbracket^{M\_{2Be3}}$ = 1 ssi $chante.avec(fr,a)$ dans $M\_{2Be3}$

Entrées lexicales:

- $\llbracket \text{Frank} \rrbracket^{M\_{2Be3}} = fr\_{e}$  
- $\llbracket \text{Adel} \rrbracket^{M\_{2Be3}} = a\_{e}$  
- $\llbracket \text{chante avec} \rrbracket^{M\_{2Be3}} = \lambda y. \lambda x. chanter.avec (x,y)\_{\langle e, \langle e,t \rangle \rangle}$  

Composition:

1. $\llbracket \text{chante avec} \rrbracket^{M\_{2Be3}}(\llbracket \text{Adel} \rrbracket^{M\_{2Be3}}) = \[\lambda y. \lambda x. chanter.avec (x,y)\]\\_{\langle e, \langle e,t \rangle \rangle}(a)\\_{e} = \lambda x. chanter.avec(x,a)\\_{\langle e,t \rangle}$
2. $\llbracket \text{chante avec Adel} \rrbracket^{M\_{2Be3}}(\llbracket \text{Frank} \rrbracket^{M\_{2Be3}}) = \[\lambda x. chanter.avec(x,a)\]\\_{\langle e,t \rangle}(fr\\_{e}) = chanter.avec(fr,a)\\_{t}$

Dénotation:

(1) $\llbracket \text{Frank chante avec Adel} \rrbracket^{M\_{2Be3}}$ = 1

---


1. Frank danse avec Filip.

   Composition:

   1. $\llbracket \text{danse avec} \rrbracket^{M_{2Be3}}(\llbracket \text{Filip} \rrbracket^{M_{2Be3}}) = \[\lambda y. \lambda x. danser.avec (x,y)\]_{\langle e, \langle e,t \rangle \rangle}(fi)_{e} = \lambda x. danser.avec(x,fi)_{\langle e,t \rangle}$
   2. $\llbracket \text{danse avec Filip} \rrbracket^{M_{2Be3}}(\llbracket \text{Frank} \rrbracket^{M_{2Be3}}) = \lambda x. chanter.avec(x,fi)_{\langle e,t \rangle}(fr_{e}) = danser.avec(fr,fi)_{t}$
   
   Dénotation:

   $\llbracket \text{Frank danse avec Filip} \rrbracket^{M_{2Be3}} = 0$

2. Filip est le leader.  
   
   Entrées lexicales:

   $\llbracket \text{leader} \rrbracket = \lambda x. leader(x)_{\langle e,t \rangle}$

   Composition:

   1. $\llbracket \text{est} \rrbracket^{M_{2Be3}}(\llbracket \text{le leader} \rrbracket^{M_{2Be3}}) = \[\lambda P. P_{\langle \langle e,t \rangle, \langle e,t \rangle \rangle}\](\lambda x. leader(x)_{\langle e,t \rangle}) = \lambda x. leader(x)_{\langle e,t \rangle}$
   2. $\llbracket \text{est le leader} \rrbracket^{M_{2Be3}}(\llbracket \text{Filip} \rrbracket^{M_{2Be3}}) = \[(\lambda x. leader(x))_{\langle e,t \rangle}\](fi_{e}) = leader(fi)_{t}$
   
   Dénotation:

   $\llbracket \text{Filip est le leader} \rrbracket^{M_{2Be3}} = 1$


3. Adel fait un airflare.  
*$\equiv$ "Adel airflare"; dans cette position, l'article indéfini n'est pas interprété sémantiquement.*

    Entrées lexicales:

    $\llbracket \text{faire un airflare} \rrbracket = \lambda x. airflare(x)_{\langle e,t \rangle}$

    Composition:

   $\llbracket \text{fait un airflare} \rrbracket^{M_{2Be3}}(\llbracket \text{Adel} \rrbracket^{M_{2Be3}}) = \[\lambda x. airflare(x)_{\langle e,t \rangle}\](a_{e}) = airflare(a)_{t}$
   
   
   Dénotation:

   $\llbracket \text{Adel fait un airflare} \rrbracket^{M_{2Be3}} = 1$

1. Frank n'est pas content.
   
   Entrées lexicales:

   $\llbracket \text{content} \rrbracket = \lambda x. content(x)_{\langle e,t \rangle}$

   Composition:

   1. $\llbracket \text{est} \rrbracket^{M_{2Be3}}(\llbracket \text{content} \rrbracket^{M_{2Be3}}) = \[\lambda P. P_{\langle \langle e,t \rangle, \langle e,t \rangle \rangle}\](\lambda x. content(x)_{\langle e,t \rangle}) = \lambda x. content(x)_{\langle e,t \rangle}$
   2. $\llbracket \text{est content} \rrbracket^{M_{2Be3}}(\llbracket \text{Neg} \rrbracket^{M_{2Be3}}) = \[\lambda x. content(x)_{\langle e,t \rangle}\](\lambda P. \lambda x. \neg P(x)_{\langle \langle e,t \rangle, \langle e,t \rangle \rangle}) = \lambda x. \neg content(x)_{\langle e,t \rangle}$
   3. $\llbracket \text{n'est pas content} \rrbracket^{M_{2Be3}}(\llbracket \text{Frank} \rrbracket^{M_{2Be3}}) = \[\lambda x. \neg content(x)_{\langle e,t \rangle}\](fr_{e}) = \neg content(fr)_{t}$
   
   Dénotation:

   $\llbracket \text{Frank n'est pas content} \rrbracket^{M_{2Be3}} = 1 \lor 0$

2. Adel et Frank sont jaloux de Filip.

    Entrées lexicales:

    $\llbracket \text{jaloux} \rrbracket = \lambda y. \lambda x. jaloux(x,y)_{\langle e ,\langle e,t \rangle \rangle}$

    Composition:

    1. $\llbracket \text{de} \rrbracket^{M_{2Be3}}(\llbracket \text{Filip} \rrbracket^{M_{2Be3}}) = \[\lambda x. x_{\langle e,e \rangle}\](fi_{e}) = fi_{e}$
    2. $\llbracket \text{jaloux} \rrbracket^{M_{2Be3}}(\llbracket \text{de Filip} \rrbracket^{M_{2Be3}}) = \[\lambda y\lambda x. jaloux(x,y)_{\langle e, \langle e,t \rangle \rangle}\](fi_{e}) = \lambda x. jaloux(x,fi)_{\langle e,t \rangle}$
    3. $\llbracket \text{sont} \rrbracket^{M_{2Be3}}(\llbracket \text{jaloux de Filip} \rrbracket^{M_{2Be3}}) = \[\lambda P. P_{\langle \langle e, t \rangle, \langle e,t \rangle \rangle}\](\lambda x. jaloux(x,fi)_{\langle e,t \rangle}) = \lambda x. jaloux(x,fi)_{\langle e,t \rangle}$
    4. $\llbracket \text{et} \rrbracket^{M_{2Be3}}(\llbracket \text{Frank} \rrbracket^{M_{2Be3}}) = \[\lambda y. \lambda x. x \oplus y_{\langle e, \langle e,e \rangle \rangle}\](fr_{e}) = \lambda x. x \oplus fr_{\langle e,e \rangle}$
    5. $\llbracket \text{et Frank} \rrbracket^{M_{2Be3}}(\llbracket \text{Adel} \rrbracket^{M_{2Be3}}) = \[\lambda x. x \oplus fr_{\langle e,e \rangle}\](a_{e}) = a \oplus fr_{e}$
    6. $\llbracket \text{sont jaloux de Filip} \rrbracket^{M_{2Be3}}(\llbracket \text{Adel et Frank} \rrbracket^{M_{2Be3}}) = \[\lambda x. jaloux(x,fi)_{\langle e,t \rangle}\](a \oplus fr_{e}) = jaloux(a \oplus fr, fi)_{t}$

    Dénotation:

    $\llbracket \text{Adel et Frank sont jaloux de Filip} \rrbracket^{M_{2Be3}} = 1 \lor 0$


3. Filip, Adel et Frank ont des abdos.  
   *$\equiv$ "Filip et Adel et Frank ont des abdos"*

   Entrées lexicales:

   $\llbracket \text{avoir des abdos} \rrbracket = \lambda x. abdos(x)_{\langle e,t \rangle}$

   Composition:

   1. $\llbracket \text{et} \rrbracket^{M_{2Be3}}(\llbracket \text{Frank} \rrbracket^{M_{2Be3}}) = \[\lambda y. \lambda x. x \oplus y_{\langle e, \langle e,e \rangle \rangle}\](fr_{e}) = \lambda x. x \oplus fr_{\langle e,e \rangle}$
   2. $\llbracket \text{et Frank} \rrbracket^{M_{2Be3}}(\llbracket \text{Adel} \rrbracket^{M_{2Be3}}) = \[\lambda x. x \oplus fr_{\langle e,e \rangle}\](a_{e}) = a \oplus fr_{e}$
   3. $\llbracket \text{et} \rrbracket^{M_{2Be3}}(\llbracket \text{Filip} \rrbracket^{M_{2Be3}}) = \[\lambda y. \lambda x. x \oplus y_{\langle e, \langle e,e \rangle \rangle}\](fi_{e}) = \lambda x. x \oplus fr_{\langle e,e \rangle}$
   4. $\llbracket \text{et Filip} \rrbracket^{M_{2Be3}}(\llbracket \text{Frank et Adel} \rrbracket^{M_{2Be3}}) = \[\lambda x. x \oplus fr \oplus a_{\langle e,e \rangle}\](fi_{e}) = fr \oplus a \oplus fi_{e}$
   5. $\llbracket \text{ont des abdos} \rrbracket^{M_{2Be3}}(\llbracket \text{Filip, Adel et Frank} \rrbracket^{M_{2Be3}}) = \[\lambda x. abdos(x)_{\langle e,t \rangle}\](fr \oplus a \oplus fi_{e}) = abdos(fr \oplus a \oplus fi)_{t}$
   
   Dénotation:
   
   $\llbracket \text{Filip, Adel et Frank ont des abdos} \rrbracket^{M_{2Be3}} = 1$


4. Filip chante et Frank danse avec Adel.

    Entrées lexicales:

    $\llbracket \text{chante} \rrbracket = \lambda x. chante(x)_{\langle e,t \rangle}$

    Composition:

    1. $\llbracket \text{chante} \rrbracket^{M_{2Be3}}(\llbracket \text{Filip} \rrbracket^{M_{2Be3}}) = \[\lambda x. chante(x)_{\langle e,t \rangle}\](fi_{e}) = chante(fi)_{t}$
    2. $\llbracket \text{danse avec} \rrbracket^{M_{2Be3}}(\llbracket \text{Adel} \rrbracket^{M_{2Be3}}) = \[\lambda y.\lambda x. danser.avec(x,y)_{\langle e, \langle e,t \rangle \rangle}\](a_{e}) = \lambda x.danser.avec(x,a)_{\langle e,t \rangle}$
    3. $\llbracket \text{danse avec Adel} \rrbracket^{M_{2Be3}}(\llbracket \text{Frank} \rrbracket^{M_{2Be3}}) = \[\lambda x.danser.avec(x,a)_{\langle e,t \rangle}\](fr_{e}) = danser.avec(fr,a)_{t}$
    4. $\llbracket \text{et} \rrbracket^{M_{2Be3}}(\llbracket \text{Frank danse avec Adel} \rrbracket^{M_{2Be3}}) = \[\lambda p. \lambda q. p \land q_{{\langle t, \langle t,t \rangle \rangle}}\](danser.avec(fr,a)_{t}) = \lambda p. p \land danser.avec(fr,a)_{\langle t,t \rangle}$
    5. $\llbracket \text{et Frank danse avec Adel} \rrbracket^{M_{2Be3}}(\llbracket \text{Filip chante} \rrbracket^{M_{2Be3}}) = \[\lambda p. p \land danser.avec(fr,a)_{\langle t,t \rangle}\](chante(fi)_{t}) = chante(fi) \land danser.avec(fr,a)_{t}$
   
   Dénotation:

   $\llbracket \text{Filip chante et Frank danse avec Adel} \rrbracket^{M_{2Be3}} = 1$


5. Adel et Frank ne font pas de backflip.
   
   Composition:

   1. $\llbracket \text{font un backflip} \rrbracket^{M_{2Be3}}(\llbracket \text{Neg} \rrbracket^{M_{2Be3}}) = \[\lambda x. backflip(x)_{\langle e,t \rangle}\](\lambda P. \lambda x. \neg P(x)_{\langle \langle e,t \rangle, \langle e,t \rangle \rangle}) = \lambda x. \neg backflip(x)_{\langle e,t \rangle}$
   2. $\llbracket \text{et} \rrbracket^{M_{2Be3}}(\llbracket \text{Adel} \rrbracket^{M_{2Be3}}) = \[\lambda y. \lambda x. x \oplus y_{\langle e, \langle e,e \rangle \rangle}\](a_{e}) = \lambda x. x \oplus a_{\langle e,e \rangle}$
   3. $\llbracket \text{et Adel} \rrbracket^{M_{2Be3}}(\llbracket \text{Frank} \rrbracket^{M_{2Be3}}) = \[\lambda x. x \oplus a_{\langle e,e \rangle}\](fr_{e}) = fr \oplus a_{e}$
   4. $\llbracket \text{font un backflip} \rrbracket^{M_{2Be3}}(\llbracket \text{Frank et Adel} \rrbracket^{M_{2Be3}}) = \[\lambda x. \neg backflip(x)_{\langle e,t \rangle}\](fr \oplus a_{e}) = \neg backflip(fr \oplus a)_{t}$
   
   Dénotation:

   $\llbracket \text{Frank et Adel ne font pas de backflip} \rrbracket^{M_{2Be3}} = 1$

---

**Nouvelles entrées lexicales:**

$\llbracket \text{Neg} \rrbracket = \lambda P. \lambda x. \neg P(x)\_{\langle \langle e,t \rangle, \langle e,t \rangle \rangle}$ 

$\llbracket \text{est, sont} \rrbracket = \lambda P. P\_{\langle \langle e,t \rangle, \langle e,t \rangle \rangle}$  

*Une fonction d'identité sur des prédicats.*

$\llbracket \text{de} \rrbracket = \lambda x.x\_{\langle e,e \rangle}$

*Une fonction d'identité sur des individus.*

$\llbracket \text{et} \rrbracket = \lambda p. \lambda q. p \land q\_{\langle t, \langle t,t \rangle \rangle}$

*L'entrée standard de la conjonction. $p$ et $q$ sont des variables sur des propositions.*

$\llbracket \text{et}\_{individus} \rrbracket = \lambda y. \lambda x. x \oplus y\_{\langle e, \langle e,e \rangle \rangle}$  

*Le symbole $\oplus$ est issu des travaux de Link (1983) sur la pluralité et désigne la pluralité formée par deux individus/atomes; ainsi, cette entrée prend deux individus de type $e$ et retourne un individu pluriel composé de ces deux individus, également de type $e$.*

$\llbracket \text{et}\_{prédicats} \rrbracket = \lambda Q. \lambda P. \lambda x. P(x) \land Q(x)\_{\langle e,t \langle \langle e,t \rangle, \langle e,t \rangle \rangle \rangle}$  

*Cette entrée de* et *permet de conjoindre deux prédicats.*

---

**Références**

Link, Godehard (1983). "The logical analysis of plurals and mass terms: A lattice-theoretical approach". In Rainer Bäuerle, Christoph Schwarze, and Arnim von Stechow (eds.), *Meaning, Use and Interpretation of Language*, 302–323. Berlin: de Gruyter.
