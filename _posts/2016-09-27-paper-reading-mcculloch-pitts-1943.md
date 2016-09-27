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
