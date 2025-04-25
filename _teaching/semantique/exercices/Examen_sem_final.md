---
title: "Sémantique formelle, examen final"
permalink: semantique/exercices/Examen_sem_final/
layout: archive
published: true
hidden: true
---

Vienne, 1786. Lorsque Wolfgang A. Mozart propose à Lorenzo Da Ponte d'adapter pour l'opéra une pièce française subversive et accablée par la censure d'un nouveau noble impertinent, Pierre Augustin Caron de Beaumarchais, il ne se doute pas qu'il est sur le point de changer pour toujours l'histoire de la musique occidentale en composant *Les noces de Figaro*, aujourd'hui encore l'opéra le plus joué au monde et considéré comme l'une des plus grandes oeuvres lyriques jamais composées.

*Les noces de Figaro* nous racontent les aventures d'un valet au fort caractère, Figaro, qui tente d'empêcher son maître abusif, le Comte Almaviva, de séduire et de coucher avec sa fiancée, la belle soubrette Suzanne. En faisant alliance avec la Comtesse, délaissée par un époux qu'elle aime encore, Figaro et Suzanne parviendront à mettre à jour les odieux plans du Comte et à s'unir, au terme d'une journée riche en quiproquos tous plus drôlatiques les uns que les autres. Dans un célèbre passage de l'acte IV, le Comte fait des avances à sa propre femme la Comtesse, déguisée en Suzanne, qui voit ainsi ses craintes confirmées; surpris par l'arrivée de Figaro, tous deux s'éclipsent alors qu'arrive Suzanne, elle-même déguisée en Comtesse. Figaro l'ayant reconnue, ce dernier décide de lui jouer un tour en prétendant la séduire, ce qui lui vaudra une sévère volée de gifles de la part de sa future épouse lorsque celle-ci le reconnaîtra. Mais le Comte, qui a été alerté par ces bruits, surprend les deux amants, pensant ainsi que son valet tente de séduire sa propre femme. Ivre de colère, celui-ci s'apprête à châtier Figaro lorsque rentre à son tour la Comtesse, ôtant son déguisement et signifiant par là au Comte qu'elle l'a pris la main au collet. [Dans le plus beau *finale* de toute l'histoire de l'opéra](https://www.youtube.com/watch?v=aE5EtS-b2pc), le Comte demande pardon à la Comtesse, que celle-ci lui accorde, demandant que le Comte pardonne à son tour à Figaro et bénisse ses noces avec Suzanne.

*Le Mariage de Figaro ([Actes I-II](https://www.youtube.com/watch?v=cN0-kbBSDHY), [actes III-IV](https://www.youtube.com/watch?v=aE5EtS-b2pc)), direction: Karl Boehm (Philharmonique de Vienne), mise en scène: Jean-Pierre Ponnelle, avec: Hermann Prey (Figaro), Mirella Freni (Suzanne), Dietrich Fischer-Dieskau (le Comte Almaviva), Kiri Te Kanawa (la Comtesse Almaviva), Maria Ewing (Chérubin).*

---

Considérons donc le modèle $M\_{F}$ suivant:

$$
D_{M_{F}} = \{ \text{Figaro, Suzanne, la Comtesse, le Comte, Chérubin}
\}
$$

$$
M_{F} =
\left [ \begin{aligned}
  &f \rightarrow \text{Figaro} \\
  &s \rightarrow \text{Suzanne} \\
  &ca \rightarrow \text{la Comtesse} \\
  &ce \rightarrow \text{le Comte} \\
  &ch \rightarrow \text{Chérubin} \\
\end{aligned} \right ]
$$

Calculez la dénotation des expressions suivantes dans $M\_{F}$, d'après le modèle suivant:

(1) $\llbracket \text{Figaro aime Suzanne} \rrbracket^{M\_{F}} = 1$ ssi $aime(f,s)\_{t}$

Entrées lexicales:

$\llbracket \text{aime} \rrbracket = \lambda y. \lambda x. aime(x,y)\_{\langle e, \langle e,t \rangle \rangle}$

Composition:

1. $\[\llbracket \text{aime} \rrbracket\](\llbracket \text{Suzanne} \rrbracket) = \[\lambda y. \lambda x. aime(x,y)\_{\langle e, \langle e,t \rangle \rangle}\](s\_{e}) = \lambda x. aime(x,s)\_{\langle e,t \rangle}$
2. $\[\llbracket \text{aime Suzanne} \rrbracket\](\llbracket \text{Figaro} \rrbracket) = \[\lambda x. aime(x,s)\_{\langle e,t \rangle}\](f\_{e}) = aime(f,s)\_{t}$

*Nota: afin de simplifier les résultats, vous n'avez pas besoin de retranscrire la dénotation; il suffit que vous soyez arrivés à un type en $t$, puisque toutes les expressions que nous calculons sont des propositions.*

---

1. Le Comte séduit Suzanne.
2. Suzanne est amoureuse de Figaro.
3. Chérubin est un adolescent.  
   *$\equiv$ Chérubin est adolescent*
4. La comtesse est déguisée en Suzanne et Suzanne est déguisée en Comtesse
5. Le Comte n'est pas honnête.
6. Suzanne présente Chérubin à la Comtesse.
7. Figaro et Suzanne se marient.

---

**Nouvelles entrées lexicales:**

$\llbracket \text{se} \rrbracket = \llbracket \text{réflexif} \rrbracket = \lambda P. \lambda x. P(x,x)\_{\langle \langle e, \langle e, t \rangle \rangle, \langle e,t \rangle \rangle}$

*L'entrée du morphème correspondant au pronom réflexif en français. Ce prédicat est une fonction prenant comme un argument un prédicat binaire de type $\langle e, \langle e,t \rangle \rangle$ (avec deux arguments) et retourne un prédicat unaire de type $\langle e,t \rangle$, en saturant un de ses arguments par lui-même, c'est-à-dire en le réflexivisant.*

*Exemple:*

$\llbracket \text{laver} \rrbracket = \lambda y. \lambda x. laver(x,y)\_{\langle e, \langle e, t \rangle \rangle}$

$\llbracket \text{se} \rrbracket (\llbracket \text{laver} \rrbracket) = \[\lambda P. \lambda x. P(x,x)\_{\langle \langle e, \langle e, t \rangle \rangle, \langle e,t \rangle \rangle}\](\lambda y. \lambda x. laver(x,y)\_{\langle e, \langle e, t \rangle \rangle}) = \lambda x. laver(x,x)\_{\langle e,t \rangle}$

---

$\llbracket \text{présenter} \rrbracket = \lambda z. \lambda y. \lambda x. presente(x,y,z)\_{\langle e, \langle e, \langle e,t \rangle \rangle \rangle}$

*Un verbe ditransitif, c'est-à-dire un prédicat prenant trois arguments de type $e$.*

---

$\llbracket \text{est} \rrbracket = \lambda P. P\_{\langle \langle e,t \rangle, \langle e,t \rangle \rangle}$  

$\llbracket \text{sont} \rrbracket = \lambda P. P\_{\langle \langle e,t \rangle, \langle e,t \rangle \rangle}$  

*Des fonctions d'identité sur des prédicats.*

---

$\llbracket \text{de} \rrbracket = \lambda x.x\_{\langle e,e \rangle}$  

$\llbracket \text{en} \rrbracket = \lambda x.x\_{\langle e,e \rangle}$

*Des fonctions d'identité sur des individus.*

---

$\llbracket \text{et} \rrbracket = \lambda p. \lambda q. p \land q\_{\langle t, \langle t,t \rangle \rangle}$

*L'entrée standard de la conjonction. $p$ et $q$ sont des variables sur des propositions.*

---

$\llbracket \text{et}\_{individus} \rrbracket = \lambda y. \lambda x. x \oplus y\_{\langle e, \langle e,e \rangle \rangle}$  

*L'opérateur de sommation $\oplus$ est issu des travaux de Link (1983) sur la pluralité et désigne la pluralité formée par deux individus/atomes; ainsi, cette entrée prend deux individus de type $e$ et retourne un individu pluriel composé de ces deux individus, également de type $e$.*

---

$\llbracket \text{et}\_{prédicats} \rrbracket = \lambda Q. \lambda P. \lambda x. P(x) \land Q(x)\_{\langle e,t \langle \langle e,t \rangle, \langle e,t \rangle \rangle \rangle}$  

*Cette entrée de* et *permet de conjoindre deux prédicats.*

---

$\llbracket \text{Neg} \rrbracket = \lambda P. \lambda x. \neg P(x)\_{\langle \langle e,t \rangle, \langle e,t \rangle \rangle}$

---

**Références**

Link, Godehard (1983). "The logical analysis of plurals and mass terms: A lattice-theoretical approach". In Rainer Bäuerle, Christoph Schwarze, and Arnim von Stechow (eds.), *Meaning, Use and Interpretation of Language*, 302–323. Berlin: de Gruyter.
