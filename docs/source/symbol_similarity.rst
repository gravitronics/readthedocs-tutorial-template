SymbolSimilarity
================

``SymbolSimilarity`` is a class that encapsulates the similarity
computations between symbols represented in a ``SymbolEmbeddingMap``. It
provides methods to generate a similarity matrix, retrieve the nearest
symbols for a query_text, and transform the similarity matrix.
``SymbolSimilarity`` is useful for identifying similar symbols in the
code based on their embedding vectors provided by the
``SymbolEmbeddingMap``.

Overview
--------

``SymbolSimilarity`` is initialized with a ``SymbolEmbeddingMap`` and an
optional normalization type (``NormType``). It can generate a similarity
matrix for all symbols in the embedding map using the
``generate_similarity_matrix`` method. The closest symbols for a query
can be found using the ``get_nearest_symbols_for_query`` method, which
returns a dictionary mapping the nearest symbols to their similarity
scores. The similarity matrix can be transformed using the
``transform_similarity_matrix`` method.

Methods
-------

-  ``generate_similarity_matrix``: Generates a similarity matrix for all
   symbols in the embedding map.
-  ``get_nearest_symbols_for_query``: Gets the k most similar symbols to
   the query_text.
-  ``transform_similarity_matrix``: Transforms the similarity matrix
   based on a given query_text.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_rank.symbol_embedding_map.SymbolEmbeddingMap``
-  ``automata.core.search.symbol_rank.symbol_similarity.SymbolSimilarity``

Example
-------

The following example demonstrates how to create an instance of
``SymbolSimilarity``, generate a similarity matrix, and retrieve the
nearest symbols for a query.

.. code:: python

   from automata.core.search.symbol_rank.symbol_similarity import SymbolSimilarity
   from automata.core.search.symbol_rank.symbol_embedding_map import SymbolEmbeddingMap

   symbol_embedding_map = SymbolEmbeddingMap()
   symbol_similarity = SymbolSimilarity(symbol_embedding_map)

   similarity_matrix = symbol_similarity.generate_similarity_matrix()
   nearest_symbols = symbol_similarity.get_nearest_symbols_for_query("example_query", k=5)

Limitations
-----------

``SymbolSimilarity`` relies on the embedding_dict provided by
``SymbolEmbeddingMap``. As such, it inherits the limitations of the
provided embeddings, which do not account for code semantics and are
limited by the vector representations of the symbols. Furthermore,
``SymbolSimilarity`` assumes a specific structure for the embedding_dict
and cannot handle custom representations.

Follow-up Questions:
--------------------

-  How can we include custom representations for symbols to be used in
   similarity calculations?
