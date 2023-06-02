SymbolEmbeddingMap
==================

``SymbolEmbeddingMap`` is a class that manages the embeddings for a set
of symbols and provides methods to build, load, filter, update, and save
the embedding map. The class is mainly used as a wrapper around the
symbol embeddings and provides necessary methods for interacting with
them, such as getting the embeddings for a specific subset of symbols or
updating the embeddings for a set of symbols.

Overview
--------

``SymbolEmbeddingMap`` provides the functionality to build a new
embedding map using given symbols, load an existing embedding map from a
file, update the embeddings for a selected set of symbols, filter the
embedding map to only contain entries for the selected symbols, and save
the embeddings to a file for future use.

The class is closely related to ``Symbol`` objects and depends on an
``embedding_provider`` object to obtain embeddings. The
``embedding_provider`` object defaults to an ``EmbeddingsProvider()``
instance, which can be replaced with a custom provider if necessary.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_types.SymbolEmbedding``
-  ``automata.core.search.symbol_rank.symbol_similarity.SymbolSimilarity``
-  ``automata.core.search.symbol_factory.SymbolEmbeddingMapFactory``

Example
-------

The following is an example demonstrating how to create an instance of
``SymbolEmbeddingMap`` using a dictionary of embeddings.

.. code:: python

   from automata.core.search.symbol_rank.symbol_embedding_map import SymbolEmbeddingMap

   # Define the embedding dictionary with Symbol and SymbolEmbedding objects
   embedding_dict = {...}

   # Create an instance of SymbolEmbeddingMap
   sem_map = SymbolEmbeddingMap(load_embedding_map=True, embedding_dict=embedding_dict)

Limitations
-----------

The primary limitation of ``SymbolEmbeddingMap`` is that it assumes a
specific structure for its input and output data formats. The embeddings
need to be provided as a dictionary of ``Symbol`` objects and
``SymbolEmbedding`` objects, which may not be directly compatible with
other embedding formats.

The class also depends on a specific ``embedding_provider``, which
defaults to ``EmbeddingsProvider()``. This can be replaced with a custom
provider; however, the custom provider must work within the constraints
and assumptions made by the ``SymbolEmbeddingMap`` class.

Follow-up Questions:
--------------------

-  Can ``SymbolEmbeddingMap`` be easily adapted to work with alternative
   data formats or embedding providers?
