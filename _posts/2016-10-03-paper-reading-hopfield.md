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
    Thus, each neuron randomly and asynchronously evaluates
    whether it is above or below threshold and readjusts accordingly.
    (Unless otherwise stated, we choose $$U_{i}=0$$.)

+   Differences with Perceptron
    +   Perceptrons were modeled chiefly with neural connections in a
        "forward" direction $$A\rightarrow B\rightarrow C\rightarrow D$$.
        All our interesting results arise as consequences of the strong
        back-coupling.
    +   Perceptron studies usually made a random net of neurons deal directly
        with a real physical world and did not ask the questions essential
        to finding the more abstract emergent computational properties.
    +   Perceptron modeling required synchronous neurons like a conventional
        digital computer. There would be no way to use global synchrony
        effectively.

### The information storage algorithm

+   Suppose we wish to store the set of states $$V^{s}, s=1,\cdots, n$$. We
    use the storage prescription:

    $$
    T_{ij}=\sum_{s}(2V_{i}^{s}-1)(2V_{j}^{s}-1)
    $$

    but with $$T_{ii}=0$$. From this definition

    $$
    \sum_{j}T_{ij}V_{j}^{s'}=\sum_{s}(2V_{i}^{s}-1)\left[\sum_{j}V_{j}^{s'}(2V_{j}^{s}-1)\right]\equiv H_{j}^{s'}.
    $$

    The mean value of the bracketed term in above equation is 0 unless $s=s'$,
    for which the mean is $$N/2$$. This pseudoorthogonality yields

    $$
    \sum_{j}T_{ij}V_{j}^{s'}\equiv\langle H_{i}^{s'}\rangle \approx (2V_{i}^{s'}-1)N/2
    $$

    and is positive if $$V_{i}^{s'}=1$$ and negative if $$V_{i}^{s'}=0$$.
    Expect for the noise coming from the $$s\neq s'$$ terms, the stored state
    would always be stable under out processing algorithm.
