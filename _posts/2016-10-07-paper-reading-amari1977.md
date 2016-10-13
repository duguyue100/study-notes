---
title: Paper Reading - Neural Theory of Association and Concept-Formation
---

## Introduction

+ We rather intend to figure out possible neural mechanisms of learning, storing 
  and using knowledge which might be found __widely in the brain in various versions__.

  + help us in building more realistic models at the next stage.

+ Association Net:
  + Learning from $$k$$ pairs of stimulus patterns $$(x_{1}, z_{1}),\ldots,(x_{k}, z_{k})$$,
  + when the net receives a key pattern $$x_{\alpha} (\alpha=1,\ldots, k)$$, it correctly outputs the associated partner $$z_{\alpha}$$.
  + carried into effect through modification of the synaptic weights of the net.
  + so-called "correlation" of pattern components is memorized in the synaptic weights.
  + The correlational association works well when the patterns $$x_{1}, \ldots, x_{k}$$ are mutually orthogonal, but otherwise it __does not__ work well by virtue of the mutual interference of __superposed patterns__.

+ Concept formation net
  + receiving many stimulus patterns which are distributed in $$k$$ clusters
  + the net forms an equilibrium state corresponding to each cluster.
    + correspond to the concept patterns which the net retains.
  + After the learning is completed, the net, receiving a pattern belonging to a cluster, falls into the equilibrium state corresponding to the cluster.
  + short-term memory as recall pattern
  + long-term memory as learning weights
