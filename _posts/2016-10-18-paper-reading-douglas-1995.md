---
title: Paper Reading - Recurrent Excitation in Neocortical Circuits
---

+ Although lateral connections do occur between and across columns, most connections are made localy within the neighborhood of a 1-mm column, as Hubel and Wiesel originally suggested.

+ The neocortex is dominated by excitatory connections.

+ Moreover, about 85% of the 5000 to 10000 synapses made by excitatory neurons are on to other excitatory neurons.

+ However, feedback excitation has been almost completely neglected in favor of a simple feedforward view.

+ Most synapses onto spiny stellate cells originate from layer VI pyramids and other spiny stellate cells.

+ The current-discharge curve of a single representative neuron shows that the discharge frequency is proportional to the excitatory current delivered to the soma.

+ The neuron's firing frequency $$F$$ corresponds to the voltage across the conductance induced by the total current reaching the "soma" in our simple model of a neuron.

+ Because all synapses and neurons are assumed to be identical, we can reduce this network to a single neuron that receives a recurrent current $$I_{\text{rec}}$$ proportional to its own firing frequency $$F$$.

+ At equilibrium, the firing rate of the network $$F^{*}$$ must obey
  
  $$
  I_{\text{ff}}+\alpha F^{*}=GF^{*}
  $$

  Thus, the population is proportional to the feedforward input current, according to the expression

  $$
  F^{*}=\frac{I_{\text{ff}}}{G-\alpha}
  $$

+ If $$G>\alpha$$, the recurrent excitation within the pupulation is stable in the sense that it remains bounded without the restraint of saturation.

+ As $$\alpha$$ approaches $$G$$, the total input current is mainly attributable to the recurrent $$I_{\text{rec}} rather than the feedforward current $$I_{\text{ff}}$$ and the response of the system becomes domainated by the contribution of the recurrent pathway.

+ If $$\alpha>G$$, the open loop gain exceeds 1 and there is no equilibrium.

+ Proportional behavior can be achieved by controlling the recurrent amplification with small amounts of feedforward or feedback inhibition that affect the open loop gain.

+ If $$\beta$$ acts as an inhibitory network conductance of the opposite sign to the excitatory network conductance. The total recurrent current arriving at the soma is given by

   $$
   I_{\text{rec}}=(\alpha-\beta)F
   $$

   with a steady-state firing frequency $$F^{*}$$ given by

   $$
   I_{\text{ff}}+(\alpha-\beta)F^{*}=GF^{*}
   $$

   and an amplification factor of $$1/(G+\beta-\alpha)$$

+ The feedback inhibition mediated by linear synapses acts as a multiplicative, shunting-like inhibition that changes the gain of the cortical response to a given input current, whereas linear feedforward inhibition acts more like an offset that reduces the input current $$I_{\text{in}}$$ by a given amount.
