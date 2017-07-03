---
layout: page
permalink: /projects/
title: Personnal work 
description: "Some work"
tags: [Compilation, Coq]
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

# Toy complier for Mips-Gcc architecture

   Available [here](https://github.com/delouraoui/Mips-Gcc-Compiler).  
   Here you'll find a native compiler for MIPS 32 architecture.
   It implement a small functional language with type inference. Small but not so much... This compiler is a project was proposed by Yann Régis-Gianas 
   and Pierre Letouzey for the compilation course of the first year of CS  master of Paris 7.
    The generals features for this language are the followings:  
   <br/>
   Anonymous function:
	   
	   {% highlight haskell %}
  \x => t {% endhighlight %}
  
Pattern matching where t and eᵢ are expressions pᵢ are patterns:   
	   {% highlight agda %}
 t ? | p₁ => e₁  ... | pₙ => eₙ{% endhighlight %}
	   
Definitions of new types(Sum types,records,int,string,char,...): 
	   {% highlight agda %}
 type t = τ .{% endhighlight %}
	   
Records:    
	   {% highlight agda %}
 { l₁ : τ₁  ... lₙ : τₙ } {% endhighlight %}
Type Sum:    
	   {% highlight agda %}
 { c₁ : τ₁  ... cₙ : τₙ } {% endhighlight %}
 
Let definitions:
 {% highlight agda %}
 val x := t; exp. {% endhighlight %}	
Mutually recursive definitions:
 {% highlight agda %}
 rec x₁ := t₁ and ... and xₙ := tₙ; exp. {% endhighlight %}
Program:
	 {% highlight agda %}
 val x := t; exp. {% endhighlight %}
	 
For more details about the syntax you could look in the bnf [here](https://github.com/delouraoui/Mips-Gcc-Compiler/blob/master/documentation/compilation-m1-projet-2015-jalon-1.pdf).
This project have been realized in OCaml. The most simply way 
to install OCaml is to use [opam](https://opam.ocaml.org/doc/1.1/Quick_Install.html). Then 
you'll need to install one dependencies, which is merlin, by simply ``` opam install merlin```.	 
 To compile you'll use the following command:
```
 make
```

   This compiler has 5 compilation passes. Each of them has an interpreter and can be tested. 
   The first one is Hopix and it corresponds to the source language.  In order, we have Hobix 
   which corresponds to the elimination of pattern-matching, Fopix that explicit the closures, 
   Retrolix which erase function and allocate the memory and the last one Mips that towards the
   Mips architecture. This compiler has 5 compilation passes. Each of them has an interpreter and can be tested.
   The generic command is: 
```
./flap.native -s <source_language> -t <target_language> -V true -T true -I false -C false
``` 

Where -V is the verbose mode, -T with true enable the type checker and -I stand for enabling or disabling the interpreter.
	 
	 
# Toy complier for Jvm architecture
   Available [here](https://github.com/delouraoui/Jvm-Compiler).  
   We have also make another back-end compiler for the Hopix language 
   which aims a JVM architecture. It implement 2 
   way of compile it. One use a naïve compilation
   and the seconde use a Cps transformation to 
   compute the size max of the stack. Seconde 
   way is a good optimisation of compilation 
   of functional planguage with closures. This project 
   was realized in the compilation course of the second year 
   masters of Paris 7 given by [Pierre Letouzey](https://www.irif.fr/users/letouzey/edu).


# Consistency of Peaono arithmetics in Coq
   Available [here](https://github.com/delouraoui/Consistency-of-PA/blob/master/PA_Consistency.v).<br/>	
   The goal of this exercise is 
   to show the soundness of a transformation
   on formulae of first-order predicate logic. The transformation used in this
   project was the negated-translation of Godël.
   This translation is used as a embedding of formulas from the intuitionist logic to the classical logic.
   Using an interpretation of formula as Coq propositions, the consistency
   of Peano Arithmetic (PA) will be shown.
   This project was realized in the Proof Assistants (MPRI 2-7-2) of the MPRI
   master.
   
# Formalization in Coq of complexity of Skew lists
  Available [here](https://github.com/delouraoui/skew-list/blob/master/Skew.v).  
  This is a project realized in the course "Preuves Assistées par Ordinateur" given 
  by Pierre Letouzey. We will show the complexity and property of several operations
  overs the beautifully data structure which call Skew List. This structure was originally
  proposed by Okasaki's in his book "Purely Functional Data Structures".
	  
	
# Proof in Coq of the IE property for the Linear Substitution (Ls)
	
  Available [here].  
  
	

# Model checker for ltl formula Smt based
