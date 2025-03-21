---
title: "Exercices série 4, corrigé"
permalink: semantique/exercices/Ex4_Corr/
layout: archive
mathjax: true
published: true
hidden: true
---

## Logique des prédicats

1. Traduisez les expressions suivantes dans LPred:
   1. Tous les animaux sont des truites.  
   $\forall x. [animal(x) \rightarrow truite(x)]$
   3. Selina a faim.  
   $faim(s)$
   4. Selina joue avec Fido.  
   $joue(s,f)$
   5. Personne n'est une île.  
   $\neg \exists x. ile(x) \equiv \forall x. \neg ile(x)$
   6. Chaque étudiante s'aime.  
   $\forall x. [étudiante(x) \rightarrow aime(x,x)]$
   7. Chaque étudiante aime une étudiante.  
   $\exists y. [étudiante (y) \land [\forall x. étudiante(x) \rightarrow aime(x,y)]]$ (interprétation collective);  
   $\forall x. [étudiante(x) \rightarrow [\exists y. étudiante(y) \land aime(x,y)]]$ (interprétation distributive).
   8. Donald Trump est blond.  
   $blond(dt)$
   9. Tous les *soprani* sont des chanteuses.  
   $\forall x. [soprano(x) \rightarrow chanteuse(x)]$
   10. Aucun baryton n'est une femme.  
   $\neg \exists x. [baryton(x) \land femme(x)] \equiv \forall x. [baryton(x) \rightarrow \neg femme(x)]$
   11. Tous les chanteurs sont soit des basses, soit des barytons, soit des ténors.  
   $\forall x. [chanteur(x) \rightarrow [basse(x) \lor baryton(x) \lor ténor(x)]]$

2. Paraphrasez les expressions de LPred suivantes en français:
   1. $\exists x. [cool(x) \land swag(x)]$  
   Certaines choses sont cool et swag (la sémantique, par exemple).
   2. $\forall x. [truite(x) \land fumée(x)]$  
   Tout le monde est une truite fumée.
   3. $\forall x. [rappeur(x) \rightarrow grossier(x)]$  
   Tous les rappeurs sont grossiers.
   4. $\forall x. [rappeur(x) \rightarrow \exists y. voiture(y) \land tunée(y) \land conduire(x,y) ]$  
   Tous les rappeurs conduisent une voiture tunée (interprétation distributive: Snoop Dogg conduit une Chevrolet Impala 1967, 50 cent conduit une Lamborghini Murciélago, le Roi Heenok conduit une Pontiac, etc.)
   5. $\neg \exists x. rappeur(x) \land truite(x)$  
   Aucune truite ne rappe.
   6. $\exists x. [rappeur(x) \land \neg misogyne(x)]$  
   Certains rappeurs ne sont pas misogynes.
   7. $\forall x. [ rappeur(x) \rightarrow \exists y. \exists z. [ [limousine(y) \land chaine(z) \land or(z)] \land [avoir(x,y) \lor avoir(x,z)] ] ]$  
   Tous les rappeurs ont soit une limousine, soit une chaîne en or (possiblement les deux).
