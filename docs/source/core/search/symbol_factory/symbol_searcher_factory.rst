SymbolSearcherFactory
=====================

``SymbolSearcherFactory`` is a factory class that helps create
``SymbolSearcher`` objects using different factories and configurations
for building the necessary components. The main method available in this
class is ``create``, which allows the creation of ``SymbolSearcher``
objects by passing the required factories and configurations.

Overview
--------

``SymbolSearcherFactory`` offers a convenient way to instantiate
``SymbolSearcher`` objects with custom settings and factories. It
provides a flexible method to create a ``SymbolSearcher`` with different
``SymbolGraphFactory``, ``SymbolEmbeddingMapFactory``,
``SymbolSimilarityFactory``, and ``SymbolRankConfig`` instances. The
factory class ensures that the passed configurations are properly used
to build the necessary components for the ``SymbolSearcher``.

Related Symbols
---------------

-  ``automata.core.search.symbol_factory.SymbolGraphFactory``
-  ``automata.core.search.symbol_factory.SymbolEmbeddingMapFactory``
-  ``automata.core.search.symbol_factory.SymbolSimilarityFactory``
-  ``automata.core.search.symbol_factory.SymbolRankConfig``
-  ``automata.tool_management.symbol_searcher_manager.SymbolSearcherToolManager``
-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.tools.search.symbol_searcher.SymbolSearcher``

Example
-------

The following example demonstrates how to create a ``SymbolSearcher``
object using the ``SymbolSearcherFactory``.

.. code:: python

   from automata.core.search.symbol_factory import SymbolSearcherFactory
   from automata.core.search.symbol_factory import SymbolGraphFactory, SymbolEmbeddingMapFactory, SymbolSimilarityFactory
   from automata.core.search.symbol_factory import SymbolRankConfig

   # Create the necessary factories and configuration objects
   symbol_graph_factory = SymbolGraphFactory()
   symbol_embedding_map_factory = SymbolEmbeddingMapFactory()
   symbol_similarity_factory = SymbolSimilarityFactory()
   symbol_rank_config = SymbolRankConfig()

   # Instantiate the SymbolSearcherFactory
   factory = SymbolSearcherFactory()

   # Create a SymbolSearcher object using the created factories and configuration objects
   symbol_searcher = factory.create(
       symbol_graph_factory=symbol_graph_factory,
       symbol_embedding_map_factory=symbol_embedding_map_factory,
       symbol_similarity_factory=symbol_similarity_factory,
       symbol_rank_config=symbol_rank_config
   )

Limitations
-----------

The main limitation of the ``SymbolSearcherFactory`` is that it relies
on predefined configuration files and assumes a specific directory
structure for these files in the ``create`` method. Custom configuration
files may not be supported without modifying the method or passing
custom instances of the factories to the ``create`` method.

Follow-up Questions:
--------------------

-  How can we include custom configuration files for loading into the
   ``SymbolSearcherFactory`` class?
-  How can we make the directory structure more flexible to support
   different file organization?
