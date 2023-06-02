SymbolRankConfig
================

``SymbolRankConfig`` is a configuration class that provides the
necessary setup and settings for the ``SymbolRank`` algorithm. It
contains various attributes such as ``alpha``, ``max_iterations``,
``tolerance``, and ``weight_key`` to customize the behavior of the
SymbolRank calculations.

Overview
--------

``SymbolRankConfig`` allows for easy configuration of the SymbolRank
algorithm to account for different use cases and requirements. The class
provides validation methods to ensure that parameter values are within
acceptable bounds, such as ``alpha`` being a float in the range (0, 1)
and ``tolerance`` being a float in the range (1e-4, 1e-8). The class can
be used in conjunction with other symbols like
``automata.core.search.symbol_rank.symbol_rank.SymbolRank``,
``automata.core.search.symbol_types.Symbol``, and
``automata.core.search.symbol_rank.tests.test_symbol_rank.test_get_ranks``.

Related Symbols
---------------

-  ``automata.core.search.symbol_rank.symbol_rank.SymbolRank``
-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_rank.tests.test_symbol_rank.test_get_ranks``

Example
-------

The following is an example demonstrating how to create an instance of
``SymbolRankConfig`` with custom settings.

.. code:: python

   from automata.core.search.symbol_rank.symbol_rank import SymbolRankConfig

   config = SymbolRankConfig(alpha=0.15, max_iterations=200, tolerance=5.0e-7, weight_key="custom_weight_key")

Limitations
-----------

While ``SymbolRankConfig`` provides flexibility in terms of defining the
behavior of the SymbolRank algorithm, it does not automatically detect
the best configuration settings for a given problem. Users must possess
prior knowledge about the problem domain or experiment with different
settings to obtain improved results with the SymbolRank algorithm.

Follow-up Questions:
--------------------

-  Is there any guideline to choose the optimal values of ``alpha``,
   ``max_iterations``, and ``tolerance`` for the underlying problem?
-  What are the implications of choosing too low or too high values for
   these parameters, and how will they impact the results?
