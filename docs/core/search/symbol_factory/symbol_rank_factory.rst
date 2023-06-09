SymbolRankFactory
=================

``SymbolRankFactory`` is a class that provides a method to create
``SymbolRank`` objects. A ``SymbolRank`` object computes SymbolRank
values for nodes in a graph.

Overview
--------

The primary method provided by ``SymbolRankFactory`` is ``create``,
which takes a symbol graph and an optional configuration object as its
input and returns a new instance of ``SymbolRank``.

Related Symbols
---------------

-  ``automata.core.search.symbol_factory.SymbolFactory``
-  ``automata.core.search.symbol_rank.symbol_rank.SymbolRank``
-  ``automata.core.search.symbol_rank.symbol_rank.SymbolRankConfig``
-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_graph.SymbolGraph``

Example
-------

The following example demonstrates how to create a ``SymbolRank`` object
using a given symbol graph.

.. code:: python

   import networkx as nx
   from automata.core.search.symbol_factory import SymbolRankFactory
   from automata.core.search.symbol_graph import SymbolGraph

   # Load a symbol graph
   symbol_graph = SymbolGraph(index_path="path/to/protobuf/index")

   # Create a directed graph representation of the symbol graph
   graph = nx.DiGraph(symbol_graph._graph)

   # Create a SymbolRankFactory instance
   rank_factory = SymbolRankFactory()

   # Create a SymbolRank object using the SymbolRankFactory
   symbol_rank = rank_factory.create(graph)

Limitations
-----------

The primary limitation of ``SymbolRankFactory`` is that it only provides
support for creating ``SymbolRank`` objects and does not provide support
for creating other types of ranking objects.

Follow-up Questions:
--------------------

-  Are there plans to extend the ``SymbolRankFactory`` class to support
   the creation of other types of ranking objects, or should separate
   factory classes be created for each ranking type?
-  How can we customize the ranking process if we want to use different
   ranking algorithms?
