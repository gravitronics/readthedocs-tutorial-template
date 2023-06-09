SymbolSimilarity
================

``SymbolSimilarity`` is a class that helps compute similarity scores
between symbols using their embeddings. This class provides various
methods to compute similarity scores and generate similarity matrices
among symbols based on their embeddings.

Overview
--------

``SymbolSimilarity`` takes a ``SymbolEmbeddingMap`` as input and
computes the similarity scores using different supported normalization
types, e.g., L2 norm. It offers methods to obtain the nearest symbols to
a query text or to compute the similarity scores between all symbols.
The class also provides a way to transform the similarity matrix based
on a unitary transformation.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_similarity.SymbolSimilarityFactory``
-  ``automata.tools.search.symbol_searcher.SymbolSearcher``
-  ``automata.core.search.symbol_types.SymbolReference``

Example
-------

Here’s an example showing how to create an instance of
``SymbolSimilarity`` and use it to get the nearest symbols for a query
text.

.. code:: python

   from automata.core.search.symbol_embedding_map import SymbolEmbeddingMap
   from automata.core.search.symbol_rank.symbol_similarity import SymbolSimilarity

   symbol_embedding_map = SymbolEmbeddingMap(load_embedding_map=True)
   symbol_similarity = SymbolSimilarity(symbol_embedding_map)

   # Get the nearest symbols for a query text
   query_text = "sample query"
   nearest_symbols = symbol_similarity.get_nearest_symbols_for_query(query_text, k=5)

   print(nearest_symbols)

Limitations
-----------

The ``SymbolSimilarity`` class requires a precomputed
``SymbolEmbeddingMap`` to compute similarity scores. Moreover, it
assumes a specific format for the ``SymbolEmbeddingMap`` and may not be
compatible with custom embedding maps.

Follow-up Questions:
--------------------

-  What should be done if the ``SymbolEmbeddingMap`` is not available or
   not in the expected format?
