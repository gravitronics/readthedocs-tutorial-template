SymbolRank
==========

``SymbolRank`` is a class used to compute SymbolRank values of nodes in
a graph. It computes the SymbolRank of each node in a given graph using
a modified version of the PageRank algorithm, incorporating symbol
similarity, initial weights, and dangling nodes.

Overview
--------

The ``SymbolRank`` class offers a method called ``get_ranks`` that
computes and returns the SymbolRank of each node in the graph. The class
requires two main inputs - a graph (in the form of a NetworkX DiGraph)
and an optional configuration object (a ``SymbolRankConfig`` instance
that contains specific configurations for the ranking algorithm).

The ``get_ranks`` method takes three optional dictionaries as input -
``symbol_similarity``, ``initial_weights``, and ``dangling``. These
dictionaries allow for customization of the ranking process based on
symbol similarity values, initial weights for each node, and handling of
dangling nodes (nodes with no outgoing edges).

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.tool_management.tests.test_symbol_searcher_tool_manager.test_symbol_rank_search``
-  ``automata.core.search.symbol_rank.tests.test_symbol_rank.test_get_ranks``
-  ``automata.core.search.symbol_rank.tests.test_symbol_rank.test_get_ranks_small_graph``
-  ``automata.tool_management.symbol_searcher_manager.SearchTool``
-  ``automata.core.code_indexing.python_code_printer.CodePrinter``
-  ``automata.core.search.symbol_rank.symbol_similarity.SymbolSimilarity``

Example
-------

Here is an example demonstrating how to instantiate the SymbolRank class
and calculate ranks for a given graph.

.. code:: python

   import networkx as nx
   from automata.core.search.symbol_rank.symbol_rank import SymbolRank, SymbolRankConfig

   # Create a directed graph
   G = nx.DiGraph()
   G.add_edge(1, 2)
   G.add_edge(2, 3)
   G.add_edge(3, 1)

   # Create a SymbolRankConfig instance (optional)
   config = SymbolRankConfig()

   # Instantiate the SymbolRank class with the graph and config
   symbol_rank = SymbolRank(G, config)

   # Calculate and print the ranks
   ranks = symbol_rank.get_ranks()
   print(ranks)

Limitations
-----------

The primary limitation of the ``SymbolRank`` class is that it assumes
the input graph is a NetworkX DiGraph. If the graph is in a different
format, it would need to be converted to a NetworkX DiGraph first.
Additionally, the class only supports SymbolRank values computation for
nodes provided in the input graph, and it cannot handle dynamic graphs
or graphs with evolving node or edge weights over time.

Follow-up Questions:
--------------------

-  Can the SymbolRank class be adapted to handle other graph formats?
