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

### Model Net for Association

+ The net
  + receives $$n$$ input signals $$x_{1},\ldots, x_{n}$$ and
  + transforms them into $$m$$ output signals $$y_{1},\ldots, y_{m}$$.

+ Every input $$x_{j}$$ is connected with all the elements.

+ Let $$w_{ij}$$ be the connection weight of $$x_{j}$$ entering into the $$i$$-th element.
+ Let $$h_{i}$$ be the threshold of the $$i$$-th element.

+ The output $$y_{i}$$ is determined by

  $$
  y_{i}=\varphi\left(\sum_{j=1}^{n}w_{ij}x_{j}-h_{i}\right), i=1,\ldots, m
  $$

+ Rewrite in matrix form 
  
  $$
  \mathbf{y}=\varphi(\mathbf{W}\mathbf{x}-\mathbf{h}),
  $$

  where function $$\varphi$$ operates component-wise.

+ We symbolically write

  $$
  \mathbf{y}=\mathbf{T}\mathbf{x}
  $$

  to show $$\mathbf{x}$$ is transformed into $$\mathbf{y}$$.

+ The "teacher" signal

  $$
  \mathbf{z}=(z_{1}, \ldots, z_{m})^{\top}
  $$

  is strong, the output signal $$\mathbf{y}$$ is always set equal to $$\mathbf{z}$$
  when $$\mathbf{z}$$ arrives.

+ The "teacher" signal $$\mathbf{z}$$ arrives at the net in the learning phase only.

+ We have $$k$$ pairs of patterns $$(x_{\alpha}, z_{\alpha})$$'s. When the net,
  receiving input $$x_{\alpha}$$, outputs the associated pattern $$z_{\alpha}$$,
  i.e. when $$z_{\alpha}=Tx_{\alpha}$$ holds, we say that the net associates
  $$z_{\alpha}$$ with $$x_{\alpha}$$.


### Model Net for Concept Formation

+ We consider the net consists of $$n$$ elements.
  + Let $$x_{1}(t), \ldots, x_{n}(t)$$ be the outputs of the net at time $$t$$.

    $$
    \mathbf{x}(t)=[x_{1}(t), \ldots, x_{n}(t)]^{\top}
    $$
    
    and call it the state of the net at time $$t$$.
  + The output $$\mathbf{x}(t+1)$$ at time $$t+1$$ is determined by

    $$
    \mathbf{x}(t+1)=\varphi[\mathbf{W}\mathbf{x}(t)-\mathbf{h}]
    $$

    which we write symbolically as

    $$
    \mathbf{x}(t+1)=T\mathbf{x}(t),
    $$

    and called $$T$$ the state-transition operator.

+ A state $$\mathbf{x}$$ which satisfies $$T\mathbf{x}=\mathbf{x}$$ is called
  an equilibrium state of the net.

+ The net can have many equilibrium states.

+ The net may be regarded as a pattern generator in which patterns $$\mathbf{x}_{1},\ldots, \mathbf{x}_{k}$$
  are coded in the form of equilibria.


## Self-organization of Nerve Elements

### Convergence of learning

+ A connection weight $$w_{i}$$ of an element increases in proportion to a 
  reinforcement signal $$r_{i}$$ in the learning phase. It decays slowly at
  the same time. The rule of modification of a weight is, hence, formulated as
  
  $$
  w_{i}(t+1)=(1-c)w_{i}(t)+dr_{i}(t),
  $$

  where $$c$$ and $$d$$ are constants.

+ When $$r_{i}(t)$$ is given by $$r_{i}(t)=x_{i}(t)y(t)$$, it realizes the
  Hebbian rule.

+ When the reinforcement signal is given by $$r_{i}(t)=x_{i}(t)u(t)$$, where
  $$u(t)$$ is the potential evoked by the input $$\mathbf{x}(t)$$

  $$
  u(t)=\sum w_{j}(t)x_{j}
  $$

  we obtain a learning rule based on the potential of the neuron.

  + The reinforcement signal $$\mathbf{r}$$ is a function of input $$\mathbf{x}$$,
    $$\mathbf{w}$$, and $$z$$. We represent it by

    $$
    \mathbf{r}=\mathbf{r}(\mathbf{w}, \mathbf{x}, z)
    $$

+ Let $$\Delta \mathbf{w}(t)$$ be the increment of the connection at time $$t$$

  $$
  \Delta \mathbf{w}(t)=\mathbf{w}(t+1)-\mathbf{w}(t)
  $$

+ Then the rule of weight modification can be written as

  $$
  \Delta \mathbf{w}(t)=-c\mathbf{w}(t)+d\mathbf{r}[\mathbf{w}(t), \mathbf{x}(t), z(t)]
  $$

  for suitable positive constant $$c$$ and $$d$$. This shows the direction of modification of $$\mathbf{w}$$

+ We consider the case when there exists a function $$R(\mathbf{w}, \mathbf{x}, z)$$ for which

  $$
  \frac{\partial R}{\partial \mathbf{w}}=\mathbf{w}-\frac{d}{c}\mathbf{r}(\mathbf{w}, \mathbf{x}, z)
  $$

  holds, then

  $$
  \Delta \mathbf{w}=-c\frac{\partial R}{\partial \mathbf{w}}
  $$

  This means that $$\mathbf{w}$$ is modified in the negative direction of the gradient
  of the gradient of $$R$$ with respect to $$\mathbf{w}$$

+ Let $$L(\mathbf{w})$$ be the expected value of $$R$$ for possible inputs $$(\mathbf{x}, z)$$

  $$
  L(\mathbf{w})=\langle R(\mathbf{w}, \mathbf{x}, z)\rangle
  $$

  where $$\langle\rangle$$ denotes the expectation with respect to $$\mathbf{x}$$ and $$z$$.


+ By taking the expectation, we have
  
  $$
  \langle\Delta \mathbf{w}\rangle=-c\frac{\partial L(\mathbf{w})}{\partial \mathbf{w}}.
  $$

+ We assume in the following that the decay constant $$c$$ is sufficiently small so that
  the connection weights converge to the minimum of $$L(\mathbf{w})$$. The minimum is
  attained at $$\mathbf{w}$$ satisfying

  $$
  c\mathbf{w}=d\langle \mathbf{r}(\mathbf{w}, \mathbf{x}, z)\rangle
  $$
