********************************************************************************
GORMMS - Graphical Overview of Reproducible Models and Molecular Simulations
********************************************************************************

The Graphical Overview of Reproducible Models and Molecular Simulations (GORMMS) is an ongoing project whose aim is to provide well-documented simulation results for a variety of systems and from various simulation techniques.
The results are taken from the Data Of Reproducible Models and Molecular Simulations (DORMMS).
The results contained here are generated in-house at NIST.
It is intended to provide guides for testing codes.
Reproducing these results is a test of the correctness of codes, either written by the user or obtained elsewhere.
The explicit conditions for each of the sets of results are supplied so that meaningful comparisons of your results with the ones listed here are possible.

.. note::

   Website: https://pages.nist.gov/gormms

   Code Repository: https://github.com/usnistgov/gormms


Install
*******

.. code-block:: bash

   pip install sphinx sphinx_rtd_theme nbsphinx numpy pandas matplotlib tabulate dormms
   sudo apt install pandoc
   mkdir build
   cd build
   cmake ..
   make

.. include:: DISCLAIMER.rst

.. include:: LICENSE.rst
