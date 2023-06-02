automata.core.search.symbol_factory.SymbolSearcherFactory
=========================================================

``SymbolSearcherFactory`` is a factory class responsible for creating
``SymbolSearcher`` objects using provided factory objects for other
components like ``SymbolGraph``, ``SymbolEmbeddingMap``, and
``SymbolSimilarity``. The created ``SymbolSearcher`` object can be used
to perform symbol ranking, search, and retrieval operations on
Automata’s codebase.

Overview
--------

``SymbolSearcherFactory`` allows customization by providing your own
factory objects for creating the related components required by the
``SymbolSearcher``. It helps to maintain the separation of concerns and
create a single point of object creation for the ``SymbolSearcher``. It
also provides a convenient way to work with the closely related symbols
like ``Symbol``, ``SymbolGraph``, and ``SymbolEmbeddingMap``.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_graph.SymbolGraph``
-  ``automata.core.search.symbol_rank.symbol_embedding_map.SymbolEmbeddingMap``
-  ``automata.core.search.symbol_rank.symbol_similarity.SymbolSimilarity``
-  ``automata.core.search.symbol_rank.SymbolRank``

Example
-------

The following example demonstrates how to create an instance of
``SymbolSearcher`` using the ``SymbolSearcherFactory``.

.. code:: python

   from automata.core.search.symbol_factory import SymbolSearcherFactory
   from automata.core.search.symbol_graph import SymbolGraphFactory
   from automata.core.search.symbol_rank.symbol_embedding_map import SymbolEmbeddingMapFactory
   from automata.core.search.symbol_rank.symbol_similarity import SymbolSimilarityFactory

   factory = SymbolSearcherFactory()
   symbol_searcher = factory.create(
       SymbolGraphFactory(),
       SymbolEmbeddingMapFactory(),
       SymbolSimilarityFactory(),
   )

Limitations
-----------

``SymbolSearcherFactory`` needs access to configuration files and
expects a specific directory structure. If no custom factories are
provided, the default ones with their own limitations will be
instantiated.

Follow-up Questions:
--------------------

-  Will the ``SymbolSearcherFactory`` work with custom-made components
   that are not derived from the ones it expects?
-  In case of handling different configurations, do we need separate
   instances of ``SymbolSearcherFactory``?
