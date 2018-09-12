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
    expressions jetables [example](https://code-examples.net/fr/docs/c/language/compound_literal**
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

Plusieurs étapes sont nécessaires, pour produire un fichier binaire exécutable directement 
sur votre machine. L'ensemble de ces étapes est décrit dans le schéma suivant.
![schema de compilation](/images/chaine_de_compilation_C.jpg)

La première étape appelée pre-processing consiste à traiter toutes les instructions de pre-process 
avant la compilation. Ces instructions peuvent être considérées comme une forme de métaprogrammation 
qui permet de définir des constantes globales, d'inliner des fonctions, d'activer ou désactiver 
certaines parties du code ou encore d'importer des bibliothèques. Ces instructions débutent par le 
caractère # et voici quelques-unes d'entre elles:
{% highlight c %}
/** définir une constante globale **/
#define CONST 1
/** définir une constante de compilation **/
#define CONSTFLAG
/** importer une bibliothèque externe de la libraire c**/
#include <stdlib.h>
/** importer une bibliothèque externe locale **/
#include "my_lib.h"
/** definir une macro fonction (pseudo inlining) **/
#define add(x,y) ((x)+(y))
/** branchement conditionnel **/
#ifdef CONSTFLAG // si CONSTFLAG est défini alors exécuter ce code
// some code
#elif CONST // sinon si
// some code
#else // sinon 
// some code
#endif
{% endhighlight %}


La définition de macro est un pur remplacement syntactique opéré par le préprocesseur. 
Par exemple, si nous avions défini la macro add sans les parenthèses:
```c
#define add(x,y) (x)+(y)
```
alors l'appel à 
```c
4 * add(2,3)
```
serait réécrite par le préprocesseur en
```c
4 * 2 + 3
```
et le résultat serait 11 et non 20 comme espéré.


La seconde étape est la compilation. Cette étape transforme le programme d'origine en une suite 
d'instructions assembleur. Le code assembleur est le langage le plus proche de la machine qui 
est encore "compréhensible" pour un humain. Chacune de ces instructions correspond à une opération
que le processeur peut réaliser. Par la suite ces instructions sont traduites en séquences binaires
par l'étape que dite d'assemblage, afin d'être directement interprété par le processeur. À la suite 
de ces étapes chaque fichier source est associé à un fichier binaire appelé objet portant l'extension 
.o. Pour obtenir un exécutable il faut encore effectuer la liaison entre les différents fichiers afin 
de créer un unique fichier binaire correspondant à l'exécutable (.exe sous Windows).

### Conditions

{% highlight c %}
if (condition)
{
// some code
}
else
{
// some code
}
{% endhighlight %}

{% highlight c %}
if (condition)
// only one line
{% endhighlight %}

{% highlight c %}
if (condition_1)
{
// some code
}
else if (condition_2)
{
// some code
}
else
{
// some code
}
{% endhighlight %}

{% highlight c %}
switch (valeur)
{
case cas1: 
    instruction;
    break;
case cas2: 
    instruction;
    break;
.
.
.
case casN: 
    instruction;
    break;
default:
   instruction;
   break;
}
{% endhighlight %}
### Boucles

{% highlight c %}
while (condition)
{
// some code
}
{% endhighlight %}

{% highlight c %}
while (condition)
// only one line
{% endhighlight %}

{% highlight c %}
do
{
// some code
}
while (condition);
{% endhighlight %}


{% highlight c %}
for (initialisation1, ..., initialisationN; condition; expression1, ..., expressionN)
{
// some code
}
{% endhighlight %}

raccourci 
{% highlight c %}
for (initialisation1, ..., initialisationN; condition; expression1, ..., expressionN);
{% endhighlight %}

exemple calculer la somme de 20 premiers entiers

{% highlight c %}
for (sum = 1, i = 0; i < 20; i++)
{
   sum += sum;
}
{% endhighlight %}


### Les ruptures de séquence


```c
break
```
Interromps immédiatement la boucle dans lequel se trouve l'instruction break. 
Dans l'exemple suivant étant donné que la condition d'arrêt est 1 (équivalent à true) il est 
impossible de sortir de la boucle une fois dedans. Grâce à la condition ligne 4 il est possible 
de l'interrompre quand i > 19.
{% highlight c linenos %}
for (sum = 1, i = 0; 1; i++)
{
   sum += sum;
   if (i >= 20)
      break;
}
{% endhighlight %}

```c
continue
```
Cette instruction permet de revenir directement à la condition de test de la boucle. Par exemple 
lorsque l'on souhaite exécuter une partie du code à un certain moment et une autre par la suite.
Prenons l'exemple suivant ou l'on souhaite tout les tours pair afficher bonjours et tous les tours
impaire en revoir.

{% highlight c linenos %}
for (i = 0; 1; i++)
{
   if ( i % 2 == 0)
   {
       printf ("bonjours\n");
       continue;
   }
   printf ("en revoir\n");
   if (i >= 20)
      break;
}
{% endhighlight %}

Exercice: Combien de pairs "bonjours" ou "en revoir" seront affichées par le code ci-dessus?

```c
return
```
