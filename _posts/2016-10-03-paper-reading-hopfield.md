---
title: Paper Reading - Neural networks and physical systems with emergent collective computational abilities
---

+   Because evolution has no such plan, it becomes relevant to ask whether the
    ability of large collections of neurons to perform "computational" tasks
    may in part be a spontaneous collective consequence of having
    a large number of interacting simple neurons.

+   Do analogous collective phenomena in a system of simple interacting neurons
    have useful "computational" correlates?

+   In many physical systems, the nature of the emergent collective properties
    is insensitive to the details inserted in the model.

### The general content-addressable memory of a physical system

+   Example of item stored in memory "H. A. Kramers & G. H. Wannier Phys. Rev.
    60, 252 (1941)."

    +   A general content addressable memory would be capable of retrieving
        this entire memory item on the basis of sufficient partial information.
    +   An ideal memory could deal with errors and retrieve this reference
        even from the input "Vannier, (1941)".

+   Consider a physical system described by many coordinates
    $$X_{1}\ldots X_{N}$$, the components of a state vector $$X$$.
    Let the system have locally stable limit points $$X_{a}, X_{b}, \ldots$$.
    Then, if the system is started sufficiently near any $$X_{a}$$,
    as at $$X=X_{a}+\Delta$$, it will proceed in time until $$X\approx X_{a}$$.
    __We can regard the information stored in the system as the vectors $$X_{a}$$,
    $$X_{b},\ldots$$, The starting point $$X=X_{a}+\Delta$$ represents a
    partial knowledge of the item $$X_{a}$$, and the system then generates
    the total information $$X_{a}$$__.

### The model system

+   Each neuron $$i$$ has two states $$V_{i}=0$$ (not firing) and $$V_{i}=1$$
    (firing at maximum rate)

+   When neuron $$i$$ has a connection made to it from neuron $$j$$,
    the strength of connection is defined as $$T_{ij}$$. (Nonconnected neurons
    have $$T_{ij}\equiv 0$$)

+   The instantaneous state ofthe system is specified by listing the $$N$$
    values of $$V_{i}$$, so it is represented by a binary word of $$N$$ bits.

+   For each neuron $$i$$ there is a fixed threshold $$U_{i}$$ Each neuron
    $$i$$ readjusts its state randomly in time but with a mean attempt rate
    $$W$$, setting

    $$
    \begin{array}{l}
        V_{i}\rightarrow 1 \\
        V_{i}\rightarrow 0
    \end{array}\text{ if }\sum_{j\neq i}T_{ij}V_{j}
    \begin{array}{l}
        >U_{i} \\
        <U_{i}

    \end{array}.
    $$
