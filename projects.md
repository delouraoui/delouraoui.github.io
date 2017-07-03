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
   Here you'll find a native compiler for MIPS 32 architecture. It implements a 
   small functional language with type inference. Small but not so much... This 
   project was proposed by Yann Régis-Gianas and Pierre Letouzey for the compilation 
   course of the first year of CS  master of Paris 7. The generals features for this 
   language are the followings:  
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
 To compile you'll should use the following command:
```
 make
```

   This compiler has 5 compilation passes. Each of them has an interpreter and can be tested. 
   The first one is Hopix and it corresponds to the source language.  In order, we have Hobix 
   which corresponds to the elimination of pattern-matching, Fopix that explicit the closures, 
   Retrolix which erase function and allocate the memory and the last one Mips that towards the
   Mips architecture. Before the last pass, we do an optimization on register allocation. Typically 
   we use a graph coloring to know the usages of variables in the program which allow us to fix some 
   registers and so reduce the size of the stack at the runtime.there is sometimes a bugs in the optimization 
   process, then it can be disable if it appears! This can be done in the file RetrolixToMips.ml
   The generic command is: 
```
./flap.native -s <source_language> -t <target_language> -V true -T true -I false -C false
``` 

Where -V is the verbose mode, -T with true enable the type checker and -I stand for enabling or disabling the interpreter.
If you want generate and test a MIPS native code it could be better to use a virtual machine. For my part I advice to use 
qemu and some iso. To come up a small tutorial to make it work the native code on a virtual machine.

# Toy complier for Jvm architecture
   Available [here](https://github.com/delouraoui/Jvm-Compiler).  
    We have also make another back-end compiler for the Hopix language which 
	aims a JVM architecture. It implements 2  way of compiling it. One uses a 
	naïve compilation and the seconde uses a Cps transformation to compute the 
	size max of the stack. Seconde way is a good optimization of the compilation 
	of functional language with closures. This project was realized in the 
	compilation course of the second year masters of Paris 7 
	given by [Pierre Letouzey](https://www.irif.fr/users/letouzey/edu).


# Consistency of Peaono arithmetics in Coq
   Available [here](https://github.com/delouraoui/Consistency-of-PA/blob/master/PA_Consistency.v).<br/>	
   The goal of this exercise is to show the soundness of a transformation on formulae of first-order predicate 
   logic. The transformation used in this project was the negated-translation of Godël. This translation is used 
   as an embedding of formulas from the intuitionist logic to the classical logic. Using an interpretation of 
   formula as Coq propositions, the consistency of Peano Arithmetic (PA) will be shown. This project was realized 
   in the Proof Assistants (MPRI 2-7-2) of the MPRI master.
   
# Formalization in Coq of complexity of Skew lists
  Available [here](https://github.com/delouraoui/skew-list/blob/master/Skew.v).  
  This is a project realized in the course "Preuves Assistées par Ordinateur" given 
  by Pierre Letouzey. We will show the complexity and property of several operations 
  on the beautiful data structure which is called Skew List. This structure was originally 
  proposed by Okasaki's in his book "Purely Functional Data Structures".
	  
	
# Proof in Coq of the IE property for the Linear Substitution (Ls)
	
  Available [here](https://www-lipn.univ-paris13.fr/~mayero/IE/)  
  This work is the result of previous internships, carried out at the LIPN.
  My advisors were Micaela Mayero and Damiano Mazza. We have formalized the preservation 
  of strong normalization, which is the main result on the explicit substitutions calculus 
  called linear substitution developed by Beniamino Accattoli and Delia Kesner. 
  For more details you could look in the unpublished article about this formalization 
  [here](/links/IEproperty.pdf)
  
	

# Model checker for ltl formula Smt based
	
  Available [here](https://github.com/delouraoui/model-checker-ltl)
  This is an implementation of model checker which uses an encoding 
  of the model in the Presburger Arithmetic. This work was realized 
  under the supervision of Arnaud Sangnier and is mainly based on this paper:
  "Equivalence Between Model-Checking Flat Counter Systems and Presburger Arithmetic".
  To come up a usage notice. 
