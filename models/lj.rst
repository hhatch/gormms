**********************
Lennard-Jones (LJ)
**********************

The LJ potential energy, :math:`U` is given by

:math:`U/\epsilon = \left\{\begin{array}{lr} 4\left[\left(\frac{\sigma}{r}\right)^{12} - \left(\frac{\sigma}{r}\right)^6\right] & r \le r_c \\ 0 & r > r_c \end{array} \right.`

where :math:`r` is the distance between interaction sites, :math:`\epsilon` is the well depth, :math:`\sigma` is the distance at which the potential switches sign and :math:`r_c` is distance at which the potential is cut off.

To account for interactions beyond :math:`r_c`, assuming a unit radial distribution fuction. :footcite:p:`allen_computer_1989` :sup:`,` :footcite:p:`frenkel_understanding_2002`

:math:`U_{LRC} = \sum_i \sum_j U_{LRC}^{ij} = \sum_i \sum_j C_{ij} n_i n_j`

where :math:`i` and :math:`j` are particle types i and j, :math:`n` are the number of sites of the given type, and the constant, :math:`C_{ij}` is given by

:math:`C_{ij} = \frac{8\epsilon_{ij}\pi\sigma_{ij}^3}{3 V}\left[\frac{1}{3}\left(\frac{\sigma_{ij}}{r^c_{ij}}\right)^9 - \left(\frac{\sigma_{ij}}{r^c_{ij}}\right)^3\right]`.

Here are some results for the LJ model.

.. toctree::
   :glob:
   :maxdepth: 2

   ../../results/lj_ref_config.ipynb
   ../../results/lj_nvt_mc.ipynb

References:

.. footbibliography::
