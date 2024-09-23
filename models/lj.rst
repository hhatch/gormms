**********************
Lennard-Jones (LJ)
**********************

:math:`U/\epsilon = 4\left[\left(\frac{\sigma}{r}\right)^{12} - \left(\frac{\sigma}{r}\right)^6\right]`

Add cutoff to equation above.
Note to developers. Keep descriptions to a relative minimum and include a lot of references.
See :footcite:t:`allen_computer_1989` and :footcite:t:`frenkel_understanding_2002`.

:math:`U_{LRC} = \sum_i \sum_j U_{LRC}^{ij} = \sum_i \sum_j C_{ij} n_i n_j`

where :math:`i` and :math:`j` are particle types i and j, :math:`n` are the number of sites of the given type, and the constant, :math:`C_{ij}` is given by

:math:`C_{ij} = \frac{8\epsilon_{ij}\pi\sigma_{ij}^3}{3 V}\left[\frac{1}{3}\left(\frac{\sigma_{ij}}{r^c_{ij}}\right)^9 - \left(\frac{\sigma_{ij}}{r^c_{ij}}\right)^3\right]`

which depends only on the LennardJones parameters.

Results for the LJ model can be found here:

.. toctree::
   :glob:
   :maxdepth: 2

   ../../results/lj_ref_config.ipynb
   ../../results/lj_nvt_mc.ipynb

.. footbibliography::
