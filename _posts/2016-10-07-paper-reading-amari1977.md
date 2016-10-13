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

## Neural Models of Association and Concept-formation

### Neural Pool

![neural pool]({{site.baseurl}}/images/reading-imgs/reading-amari-1.png)

+ Neuron pools play the role of building blocks of the models in the present paper.

+ The output signal $$y$$ of the neuron pool is represented by the average pulse rate over this bundle of axons.

+ A signal $$x_{i}$$ is also carried by a bundle of axons (Fig. 1), representing the average pulse rate of the corresponding bundle.

+ Let us consider a bistable neuron pool
  + it enters the excited state when a weighted sum

    $$
    u=\sum_{\tau=1}^{n}w_{i}x_{i}
    $$

    of the input signals exceeds at threshold value $$h_{1}$$, and stays in
    that state.
  + it enters the resting state, when the weighted sum $$u$$ becomes lower than
    another threshold value $$h_{2} (h_{2}<h_{1})$$.
  + we can represent
    + high pulse rate output by $$y=1$$
    + low pulse rate output by $$y=0$$
    + The behavior can approximately be described by
      
      $$
      y=\varphi \left[\sum w_{i}x_{i}+(h_{1}-h_{2})y-h_{1}\right]
      $$

      where $$\varphi$$ is the step-function defined by

      $$
      \varphi(u)=\begin{cases}
        1, & u>0 \\
        0, & u\leq 0
      \end{cases}
      $$

    + when $$h_{1}=h_{2}$$ holds, the equation is simplified to
      
      $$
      y=\varphi\left(\sum w_{i}x_{i}-h\right)
      $$

      This is the behavior of the so-called __McCulloch-Pitts__ formal neuron.

  + We hereafter use McCulloch-Pitts formal neurons as the constituent elements
    of our neuron nets.

  + We call
    + $$w_{i}$$ the connection weight of input $$x_{i}$$
    + $$u$$ the potential

