SymbolSimilarityFactory
=======================

``SymbolSimilarityFactory`` is a class that assists in creating
``SymbolSimilarity`` objects. It provides a method ``create`` to create
a ``SymbolSimilarity`` object with a symbol embedding map and an
optional norm type. The main purpose of this class is to facilitate the
generation of symbol similarity objects by providing an easy-to-use
interface for their creation.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_rank.symbol_similarity.SymbolSimilarity``
-  ``automata.core.search.symbol_factory.SymbolSearcherFactory``
-  ``automata.core.search.symbol_factory.SymbolFactory``
-  ``automata.tool_management.symbol_searcher_manager.SymbolSearcherToolManager``
-  ``automata.core.search.symbol_rank.symbol_embedding_map.SymbolEmbeddingMap``
-  ``automata.tools.search.symbol_searcher.SymbolSearcher``

Example
-------

The following example demonstrates how to create a ``SymbolSimilarity``
object using the ``SymbolSimilarityFactory``.

.. code:: python

   from automata.core.search.symbol_factory import SymbolSimilarityFactory
   from automata.core.search.symbol_rank.symbol_embedding_map import SymbolEmbeddingMap
   from automata.core.search.symbol_rank.symbol_similarity import NormType

   symbol_embedding_map = SymbolEmbeddingMap(load_embedding_map=True)
   factory = SymbolSimilarityFactory()
   symbol_similarity = factory.create(symbol_embedding_map, NormType.L2)

Limitations
-----------

``SymbolSimilarityFactory`` depends on the availability of a
``SymbolEmbeddingMap`` object containing symbol embeddings. If this
object is not provided or does not contain embeddings for the required
symbols, the factory will not be able to create a ``SymbolSimilarity``
object.

Follow-up Questions:
--------------------

-  How does the ``SymbolEmbeddingMap`` object get constructed with the
   required embeddings?
-  What happens if the provided ``SymbolEmbeddingMap`` doesn’t contain
   the required embeddings?
