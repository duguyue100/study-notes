---
title: Paper Reading - A Logical Calculus of the Ideas Immanent in Nervous Activity
---

## Introduction

+   The nervous system is a net of neurons, each having a soma and an axon.

+   Synapses are always between the axon of one neuron and the soma of another.
    (_There is no mention of dendrites._)

+   Excitation must exceed some threshold to initiate an impulse.

+   Except for the fact and the time of its occurrence (the impulse),
    is determined by the neuron, not by the excitation.

+   The velocity along the axon varies directly with its diameter,
    (_is this still true?_)
    +   $$<1 m/s$$ in thin axons, usually short
    +   $$>150 m/s$$ in thick axons, usually long

+   _No case_ is known in which excitation through a single synapse has elicited
    a nervous impulse in any neuron.

+   Neuron _may be excited_ by impulses arriving at a sufficient number of
    neighboring synapses within the period of latent addition, which _lasts_
    less than one quarter of a millisecond.

+   Observed temporal summation of impulses at greater intervals is
    _impossible_ for single neurons. (_so the impulses has to arrive
    in a short time._)

+   Inhibition is the _termination_ or _prevention_ of the activity of one
    group of neurons by concurrent or antecedent activity of a second group.

+   The "all-or-none" law of nervous activity is sufficient to insure that
    the activity of any neuron may be represented as a proposition.

+   To each reaction of any neuron there is a corresponding assertion of a
    simple proposition.

+   We regard facilitation and extinction as dependent
    upon continuous changes in threshold related to electrical and
    chemical variables, such as after-potentials and ionic concentrations;
    and learning as an enduring change which can survive sleep, anaesthesia,
    convlusions and coma.

+   The alterations actually underlying facilitation, extinction and learning
    in no way affect the conclusions which follow from the formal treatment of
    the activity of nervous nets, and the relations of the corresponding
    propositions remain those of the logic of propositions.

## The Theory: Nets Without Circles

+   Physical assumptions for the calculus:
    1.  The activity of the neuron is an "all-or-none" process.
    2.  A certain fixed number of synapses must be excited within
        the period of latent addition in order to excite a neuron at any time,
        and this number is independent of previous activity and position on
        the neuron.
    3.  The only significant delay within the nervous system is synaptic delay.
    4.  The activity of any inhibitory synapse absolutely prevents excitation
        of the neuron at that time.
    5.  The structure of the net does not change with time.

+   We shall introduce a functor $$S$$, whose value for a property $$P$$ is the
    property which holds of a number when $$P$$ holds of its predecessor;
    it is defined by $$S(P)(t) \equiv P(Kx) . t = x'$$;
    (_so is $$S$$ is like an activation function?_)

+   we shall write  $$S^{2}\Pr$$ for $$S(S(\Pr))$$, etc.

+   The neurons of a given net $$\mathcal{N}$$ may be assigned designations
    $$c_{1}, c_{2}, \cdots, c_{n}$$.

+   $$N_{i}(t)$$ asserts that $$c_{i}$$ fires at the time $$t$$. $$N_{i}$$ is
    called the _action of_ $c_{i}$.

+   The predicates $$N_{1}, N_{2}, \cdots$$, comprise the syntactical class
    $$\mathbf{N}$$.

+   Define the _peripheral afferents_ of $$\mathcal{N}$$ as the neurons of
    $$\mathcal{N}$$ with no axons synapsing upon them. (__Input Neurons__)
    +   Let $$N_{1},\cdots, N_{p}$$ denote the actions of input neurons and
        $$N_{p+1}, N_{p+2}, \cdots, N_{n}$$ those of the rest.
    +   Then a _solution of_ $$\mathcal{N}$$ will be a class of sentences of
        the form $$S_{i}: N_{p+i}(z_{i})\equiv\Pr_{i}(N_{1}, \cdots, N_{p}, z_{i})$$
        where $$\Pr_{i}$$ contains no free variable save $$z_{i}$$ and no descriptive
        symbols save the $$\mathbf{N}$$ in the argument $$Arg$$, and possibly
        some constant sentences $$sa$$; and such that each $$S_{i}$$ is true
        of $$\mathcal{N}$$.
        (_I have a feeling it's $$p+i$$ instead of $$p+1$$_)
    +   Given a $$\Pr_{1}(^{1}p^{1}_{1}, ^{1}p^{1}_{2},\cdots,^{1}p^{1}_{p},z_{1}, s)$$,
        containing no free variable save those in its $$Arg$$, we shall say that
        it is _realizable in the narrow sense_ if there exists a net $$\mathcal{N}$$
        and a series of $$N_{i}$$ in it such that $$N_{1}(z_{1})\equiv\Pr_{i}(N_{1}, N_{2}, \cdots, z_{1}, sa_{1})$$
        is true of it, where $$sa_{1}$$ has the form $$\mathbf{N}(0)$$.
        (It seems $$N_{i}$$ only receives time, so is $$z$$ also time?)
    +   We shall call it _realizable in the extended sense_, or simply _realizable_,
        if for some $$n$$, $$S^{n}(\Pr_{1})(p_{1}, \cdots, p_{p}, z_{1}, s)$$ is
        realizable in the above sense.
    +   $$c_{p_{i}}$$ is here the realizing neuron.
    +   We shall say of two laws of nervous excitation which are such that every $S$
        which is realizable in either sense upon one supposition is also realizable,
        perhaps by a different net, upon the other, that  they are equivalent
        assumptions, in that sense.

+   A net will be called _cyclic_ if it contains a circle.

+   Let us define a _temporal propositional expression (a TPE)_ (some logical expression), designating
    a _temporal propositional function (TPF)_, by the following recursion:
    1.  A $$^{1}p^{1}[z_{1}]$$ is a TPE, where $$p_{1}$$ is a predicate-variable.
    2.  If $$\mathbf{S}_{1}$$ and $$\mathbf{S}_{2}$$ are _TPE_ containing the same free
        individual variable, so are $$S\mathbf{S}_{1}$$, $$\mathbf{S}_{1}\mathbf{v}\mathbf{S}_{2}$$ (or),
        $$\mathbf{S}_{1}.\mathbf{S}_{2}$$ (and) and $$\mathbf{S}_{i}.\sim \mathbf{S}_{2}$$ (not).
    3.  Nothing else is a _TPE_.

+   Theorem I: _Every net of order 0 can be solved in terms of temporal propositional
    expressions. (net with order 0 is the net without recurrent unit)_

    $$
    N_{i}(z_{1})\equiv S\left\{\prod_{m=1}^{q}\sim N_{jm}(z_{1}) . \sum_{\alpha\in\kappa_{i}}\prod_{s\in\alpha}N_{is}(z_{1})\right\}
    $$

    So the above equation means when all inhibitory synapses are not firing at previous time,
    and the number of excitatory neurons that fires are larger than $$\theta_{i}$$.

    So there is always a realization of net where there is no recurrent unit in there.

+   Theorem II: _Every TPE is realizable by a net of order zero._

+   Theorem III: _Let there be given a complex sentence $$\mathbf{S}_{1}$$ built up in any manner out
    of elementary sentences of the form $$p(z_{1}-zz)$$ where $$zz$$ is any numeral,
    by any of the propositional connections: negation, disjunction,
    conjunction, implication, and equivalence. Then $$\mathbf{S}_1$$ is a TPE and
    only if it is false when its constituent $$p(z_1- zz)$$ are all assumed
    false--i.e., replaced by false sentences -- or that the last line in its
    truth-table contains an 'F',--or there is no term in its Hilbert disjunctive
    normal form composed exclusively of negated terms_.
    +   in fact provide a very convenient and workable procedure for constructing
        nervous nets to order for those cases where there is no reference to
        events indefinitely far in the past in the specification of
        the conditions.
    +   Example: heat receptor $$N_{1}$$, cold receptor $$N_{2}$$, sensation of heat $$N_{3}$$,
        sensation of cold $$N_{4}$$

        $$
        N_{3}(t)\equiv N_{1}(t-1)\vee N_{2}(t-3) \wedge \sim N_{2}(t-2)
        $$

        $$
        N_{4}(t)\equiv N_{2}(t-2)\wedge N_{2}(t-1)
        $$

        Assume $$N_{2}(0)=1$$ (feel cold at $$t=0$$), and everywhere else is 0, $$N_{1}(t)=1$$ (remove cold object) when
        $$t\neq 0$$, then $$N_{3}(3)=1$$ and $$N_{4}(3)=0$$.

        Assume $$N_{2}(t)=0$$ and $$N_{1}(t)=1$$  at all the time, then
        $$N_{3}(t)=0$$ and $$N_{4}(t)=1$$

        One can rewrite above equations in a fashion which exhibits them as built out
        of their constituents by the operations in the form

        $$
        N_{3}(t)\equiv S\{N_{1}(t)\vee S[(SN_{2}(t))\wedge\sim N_{2}(t)]\}
        $$

        $$
        N_{4}(t)\equiv S\{[SN_{2}(t)]\wedge N_{2}(t)\}
        $$

+   Theorem IV: _Relative and absolute inhibition are equivalent in the extended
    sense._
    +   The case of _relative inhibition_. By this we mean the supposition that
        the firing of an inhibitory synapse does not absolutely prevent the
        firing of the neuron, but merely raises its threshold, so that a greater
        number of excitatory synapses must fire concurrently to fire it than
        would otherwise be needed.

+   Theorem V: _Extinction is equivalent to absolute inhibition_.

+   Theorem VI: _Facilitation and temporal summation may be replaced by spatial
    summation._

+   Theorem VII: _Alterable synapses can be replaced by circles._

### The Theory: Nets with Circles

### Consequences
