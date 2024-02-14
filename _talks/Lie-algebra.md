---
layout: splash
title: "Lie Algebra"
permalink: /talks/Lie-algebra
date: 2024-02-14
---


# Chapter 1 Basic Concepts

## 1.Definitions and first examples

> <font color=red>Definition.Lie algebra</font> A vector space $L$ over a field $F$, with an operation $L \times L \rightarrow L$, denote $(x,y)\mapsto [x,y]$ and called the bracket or commutator of $x$ and $y$ , is called a Lie algebra over $F$ if the following axioms are satisfied: 
  * The bracket operation is bilinear.
  * $[x,x]=0$ for all $x$ in $L$.
  * $[x,[y,z]]+[y,[z,x]]+[z,[x,y]]=0,(x,y,z\in L)$. (Jacobi identity)

> <font color=red>Definition.Isomorphic</font> We say that two Lie algebras $L,L'$ over $F$ are isomorphic if there exists a vector space isomorphism $\phi:L\rightarrow L'$ satisfying $\phi([x,y])=[\phi(x),\phi(y)]$ for all $x,y$ in $L$ (and then $\phi$ is called an isomorphism of Lie algebras).

