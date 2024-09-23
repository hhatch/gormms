**********************
Histogram Reweighting
**********************

Analysis of flat histogram simulations is greatly enhanced by the use of histogram reweighting, which allows you to obtain information continuously as a function of the macrostate's thermodynamic conjugate.
Thus, for the grand canonical ensemble with the number of particles as the macrostate, :math:`N`, we can reweight to various values of chemical potential, :math:`\mu`.
For microcanonical partition function, :math:`\Omega(N,V,U)`, canonical, :math:`Q(N,V,T)` and grand canonical, :math:`\Xi(\mu, V, T)`, the probability to observe a state, :math:`\Pi` is given by

:math:`\ln\Pi(N,U; \mu, V, \beta) = -\beta U + \beta \mu N + \ln\Omega(N,U,V) - \ln\Xi(\mu,V,T).`

Therefore, the difference between two :math:`\ln\Pi` at different values of :math:`\mu` is known within a constant, :math:`C`

:math:`\ln\Pi(N; \mu, V, \beta) = \ln\Pi_0(N; \mu_0, V, \beta) + N\beta(\mu - \mu_0) + C.`

Thus, to reweight a histogram to a different value of :math:`\mu`, use the equation above and remove the constant by renormalization, :math:`\sum \Pi = 1`.
The thermodynamic conjugate to :math:`N` is :math:`\beta\mu`, while the conjugate of :math:`U` is :math:`-\beta`.

.. footbibliography::
