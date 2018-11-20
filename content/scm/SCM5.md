+++
title = "Predicting effects on cooperatively regulated variables"
date = 2016-06-01

[taxonomies]
tags = ["sign-consistency"]
+++

**`This is work in progress! The content is still incomplete and changing.`**


This is Part 5 of the [sign consistency series](/scm).
The previous part introduced the [forward propagation rule for independent regulations](/scm/scm4#forward-propagation). 
I mentioned that there exists a second kind of regulations, cooperative dependent regulation.
While for independent regulation *i → j* a change in *i* is sufficient to cause an change in *j*,
it depends for cooperative regulations on multiple variables whether the change in *i* will have an effect on *j*.
Cooperative regulation exists in various forms in biological systems as chemical reactions that need multiple reactants or complex protein interactions. 
In this part I will show how cooperative regulations can be modeled within the sign consistency approach.

## Forward propagation in cooperatively regulated variables

Cooperative regulations are represented as distinct type of variables in our system similar to *AND* nodes of a logic network.
The basic idea behind cooperative regulation is that one needs all regulators to have an effect,
but there exist only one limiting factor.
It might be sufficient to increase (resp. decrease) one of the regulators to change the limiting factor,
but to ensure a change in the limiting factor all regulators have to increase (resp. decrease).

![QST3](/scm/QST3.png)

**Fig. 1**: Five quantitative stable states of a cooperatively regulated variable.

![COL5](/scm/COL5.png)

**Fig. 2**: Sign labeling representation of possible transitions among the states in Figure *1*.
The *~* means that the values of the input nodes have been switched left to right in the state.

Figure *1* shows exemplarily five quantitative representations of stable states of a system were one variable is cooperatively regulated by two predecessors. 
In Figure *2* we see the possible sign labelings representing different state transitions.
We see that for the cases *a* and *d* there exists an unambiguous input output behavior.
In the cases *b*-*c* and *e*-*g* we see different outputs for the same input.
In both state transitions *b* and *c* we have an increase in one of the regulators while the other regulator remains unchanged, 
but only in *c* the limiting factor has changed leading to a change in the regulated variable. 
This behavior is implemented by the following *forward propagation* rule.

**Rule 3b (forward propagation cooperative regulation)**: 0-change can only occur in a variable that does not depend on other variables with change, or if it receives opposing regulations.

*Let (V,E,σ) be an IG and V<sub>C</sub> ⊆ V cooperatively regulated variables.
Then a labeling μ : V →{+,–,0} satisfies *Rule 3b* for node i ∈ V<sub>C</sub> iff*
+ *μ(i)≠0, or*
+ *there is no edge j → i in E such that μ(j)σ(j,i) ∈{+,–}, or*
+ *there is an edge j → i in E such that σ(j,i) = 0, or*
+ *there exist at least two edges j<sub>1</sub> →i and j<sub>2</sub> →i in E such that μ(j<sub>1</sub>)σ(j<sub>1</sub>,i)+ μ(j<sub>2</sub>)σ(j<sub>2</sub>,i) = 0.*

This rule implements forward propagation by restricting the occurrence of *0*. 
In other words *Rule 3b* limits the cases were a *change* in an upstream node can have no effect on the regulated down stream node.

## Conclusion

In this part I introduced the forward propagation rule for cooperative regulations. 
In the [next part](/scm/scm6) I will introduce a consistency rule that allow us to filter unfounded self regulations. 
