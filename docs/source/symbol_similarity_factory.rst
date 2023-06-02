SymbolSimilarityFactory
=======================

``SymbolSimilarityFactory`` is a factory class that helps create
``SymbolSimilarity`` objects. It takes a ``SymbolEmbeddingMap`` object
and an optional ``NormType`` parameter to calculate similarity. The
``create`` method returns the created ``SymbolSimilarity`` object. It is
primarily used to generate a similarity model that can be used for
symbol searching and ranking.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_rank.symbol_similarity.SymbolSimilarity``
-  ``automata.core.search.symbol_factory.SymbolSearcherFactory``
-  ``automata.core.search.symbol_factory.SymbolFactory``
-  ``automata.core.search.symbol_rank.symbol_embedding_map.SymbolEmbeddingMap``

Example
-------

The following example demonstrates how to use
``SymbolSimilarityFactory`` to create a ``SymbolSimilarity`` object.

.. code:: python

   from automata.core.search.symbol_rank.symbol_embedding_map import SymbolEmbeddingMap
   from automata.core.search.symbol_factory import SymbolSimilarityFactory
   from automata.core.search.symbol_rank import NormType

   symbol_embedding_map = SymbolEmbeddingMap(...) # Load or build a symbol embedding map
   norm_type = NormType.L2

   factory = SymbolSimilarityFactory()
   symbol_similarity = factory.create(symbol_embedding_map, norm_type)

Limitations
-----------

The primary limitation of ``SymbolSimilarityFactory`` is that it relies
on a pre-built or pre-loaded ``SymbolEmbeddingMap`` object. Moreover,
the similarity model produced by the factory is dependent on the quality
and completeness of the provided symbol embeddings.

Follow-up Questions:
--------------------

-  Are there any other limitations to the ``SymbolSimilarityFactory``
   class?
-  Can the ``SymbolSimilarityFactory`` class be improved to handle
   different types of symbol embeddings?
