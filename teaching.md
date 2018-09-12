---
layout: page
permalink: /teaching/
title: Teaching 
description: "Courses"
tags: [C/C++]
---

<section id="table-of-contents" class="toc">
  <header>
    <h3 >Contents</h3>
  </header>
<div id="drawer" markdown="1">
*  Auto generated table of contents
{:toc}
</div>
</section><!-- /#table-of-contents -->

# C/C++ cours

## cours 1

### Historique C:

* Inventé en 1972 par Dennis Ritchie et Ken Thompson à Bell Labs en même temps que le 
système d'exploitation Unix. 
* Brian Kernighan aide à populariser le langage et fut le principal auteur du livre 
The C Programming Language.
* Projet de normalisation du langage C entre 1983 et 1989, donnant naissance à la norme ANSI C89
* Mise à jour de la norme ANSI en 1999 (C99) apportant d'importantes évolutions:
    * mélange des déclarations et instructions dans le code  
    ```c 
    for (int i = 0; i < 100; i++)
    ```
    * tableau à taille variable  
    ```c 
    int v = 10; int tab[v];  
    ```
    * nouveaux types de données: 
    ```c 
    bool, complex(nombre complexes), long long int 
    ```
    * commentaires de ligne //
    * littéraux composés 
    ```c 
    if ((char []) {"bonjour"} == "bonjour") 
    ```
    expression jetable..[example](https://code-examples.net/fr/docs/c/language/compound_literal)
    * possibilité d'inliner les fonctions 
* raffinement de la norme en 2011 (C11) avec notamment l'introduction du support pour la 
programmation multi-thread et un modèle mémoire (C11 memory model)
* [lien](https://fr.wikipedia.org/wiki/C_(langage))
### Historique C++:

* Créé par Bjarne Stroustrup en 1986 
* Idée donner plus d'expressivité à C principalement en introduisant les objets (d'ailleurs c++ s'appelait C with classes à ses débuts)
* Quoi de plus: 
    * Un système de type plus stricte et renforcé
    * inlining
    * arguments de fonctions par défauts 
    * constantes typées
    ```c
    const char c = 'e'; 
    ```
    * surcharge des arguments de fonctions
    * polymorphisme (templates)
    * exceptions (gestion des erreurs)
    * inférence de type et lambda expressions (c++11)
* [lien](https://fr.wikipedia.org/wiki/C%2B%2B)


### Chaine de compilation
![schema de compilation](/images/chaine_de_compilation_C.jpg)
