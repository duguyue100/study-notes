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

    The mean value of the bracketed term in above equation is 0 unless $$s=s'$$,
    for which the mean is $$N/2$$. This pseudoorthogonality yields

    $$
    \sum_{j}T_{ij}V_{j}^{s'}\equiv\langle H_{i}^{s'}\rangle \approx (2V_{i}^{s'}-1)N/2
    $$

    and is positive if $$V_{i}^{s'}=1$$ and negative if $$V_{i}^{s'}=0$$.
    Expect for the noise coming from the $$s\neq s'$$ terms, the stored state
    would always be stable under out processing algorithm.

+   Such matrices $$T_{ij}$$ have been used in theories of linear associative
    nets to produce an output pattern from a paired input stimulus,
    $$S_{1}\rightarrow O_{1}$$. A second association $$S_{2}\rightarrow O_{2}$$
    can be simultaneously stored in the same network. But the confusing simulus
    $$0.6 S_{1}+0.4 S_{2}$$ will produce a generally meaningless mixed output
    $$0.6 O_{1}+0.4 O_{1}$$.

+   Our model, in contrast, will use its strong nonlinearity to make choices,
    produce categories, and regenerate information and, with high probability,
    will generate the output $$O_{1}$$ from such a confusing mixed stimulus.

+   Our model obtains its emergent computational properties from simple
    properties of many cells rather than circuitry.

### The biological interpretation of the model

![fig1]({{ site.baseurl }}/images/reading-imgs/reading-hopfield-1.png)

+   The mean rate at which action potentials are generated is a smooth
    function of the mean membrane potential, having the general form shown
    in Fig. 1.

+   The biological information sent to other neurons often lies in a
    short-time average of the firing rate. When this is so, one can
    neglect the details of individual action potentials and regard Fig. 1 as a
    smooth input-output relationship.

+   A study of emergent collective effects and spontaneous computation
    must necessarily focus on the nonlinearity of the input-output relationship.

+   Delays in synaptic transmission (of partially stochastic character)
    and in the transmission of impulses along axons and dendrites
    produce a delay between the input of a neuron and the
    generation of an effective output. All such delays have been
    modeled by a single parameter, the stochastic mean processing time $$1/W$$.

+   The synapses are activated by arriving action potentials. The input signal
    to a cell $$i$$ can be taken to be

    $$
    \sum_{j}T_{ij}V_{j}
    $$

    where $$T_{ij}$$ represents the effectiveness of a synapse.

### Studies of the collective behaviors of the model

+   The model has stable limit points. Consider the special case
    $$T_{ij}=T_{ji}$$, and define

    $$
    E=-\frac{1}{2}\sum_{i\neq j}\sum_{i\neq j} T_{ij}V_{i}V_{j}
    $$

    $$\Delta E$$ due to $$\Delta V_{i}$$ is given by

    $$
    \Delta E=-\Delta V_{i}\sum_{j\neq i} T_{ij}V_{j}.
    $$

    Thus, the algorithm for altering $$V_{i}$$ causes $$E$$ to be a
    monotonically decreasing function. State changes will continue until a
    least (local) $$E$$ is reached. This case is isomorphic with an Ising
    model. $$T_{ij}$$ provides the role of the exchange coupling, and there
    is also an external local field at each site. When $$T_{ij}$$ is symmetric
    but has a random character (the spin glass) there are known to
    be many (locally) stable states.

+   $$H_{i}^{s'}$$ is the "effective field" on neuron $$i$$ when the state of
    the system is $$s'$$, one of the nominal memory states. The expectation
    value of this sum is $$\pm N/2$$ as appropriate. The $$s\neq s'$$ summation
    in Eq. 2 contributes no mean, but has a rms noise of $$[(n-1)N/2]^{1/2}\equiv \sigma$$.
    For $$nN$$ large, this noise is approximately Gaussian and the probability
    of an error in a single particular bit of a particular memory will be

    $$
    P=\frac{1}{\sqrt{2\pi\sigma^{2}}}\int_{N/2}^{\infty}e^{-x^{2}/2\sigma^{2}}\,dx.
    $$

+   The experimental results of half the memories being well retained
    at $$n=0.15N$$ and and the rest badly retained is expected to be true for
    all large $$N$$.

### Discussion

+   Collective computational properties spontaneously arose.

+   Memories are retained as stable entities or Gestalts and can be correctly
    recalled from any reasonably sized subpart.

+   The bridge between simple circuits and the complex computational
    properties of higher nervous systems may be the spontaneous emergence of
    new computational capabilities from the collective behavior of large
    numbers of simple processing elements.

+   Implementation of a similar model by using integrated circuits
    would lead to chips which are much less sensitive to element
    failure and soft-failure than are normal circuits.

+   Their asynchronous parallel processing capability would provide rapid
    solutions to some special classes of computational problems.
