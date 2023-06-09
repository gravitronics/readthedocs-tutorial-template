SymbolEmbeddingMap
==================

``SymbolEmbeddingMap`` is a class that manages symbol embeddings for
deductive search in Automata. It provides functionality to build and
manage an embedding map that maps symbols from the codebase to their
corresponding vector embeddings. The class also enables persisting and
loading an embedding map to/from a file. It provides methods like
``filter_embedding_map``, ``get_embedding_dict``, and others to
manipulate the internal embedding map. SymbolEmbeddingMap is closely
related to other classes like ``Symbol``\ (1), ``SymbolEmbedding``\ (2),
and ``SymbolSimilarity``\ (3).

Overview
--------

``SymbolEmbeddingMap`` can be used in two ways: either build a new
embedding map or load an existing one. During building, it expects a
list of all defined symbols to be provided and builds an embedding map
using the chosen embedding provider. When loading an existing map, it
can either load from an input file or an embedding dictionary provided
during the instantiation.

This class is useful for performing operations like filtering symbols
based on a condition or updating the embedding map with new symbols. The
class also integrates saving and loading embedding maps to/from files,
allowing for easy storage and retrieval of embeddings.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_types.SymbolEmbedding``
-  ``automata.core.search.symbol_rank.symbol_similarity.SymbolSimilarity``

Example
-------

The following example demonstrates how to create a new instance of
``SymbolEmbeddingMap`` and update it with new symbols. Note that the
given example assumes the existence of ``symbol_list``, which should be
a list of ``Symbol`` objects representing the symbols to be used in the
embedding map.

.. code:: python

   from automata.core.search.symbol_rank.symbol_embedding_map import SymbolEmbeddingMap
   from automata.embeddings.embeddings_provider import EmbeddingsProvider
   from automata.core.search.symbol_types import Symbol

   symbol_list = [...] # A list of Symbol objects to be embedded
   embedding_provider = EmbeddingsProvider()

   # Create a new SymbolEmbeddingMap with new embeddings
   sem = SymbolEmbeddingMap(all_defined_symbols=symbol_list, build_new_embedding_map=True,
                            embedding_provider=embedding_provider)

   # Update the SymbolEmbeddingMap with new symbols
   new_symbols = [...] # A list of new Symbol objects to be added/updated in the embedding map
   sem.update_embeddings(new_symbols)

Limitations
-----------

-  The primary limitation is the requirement of well-formed lists of
   symbols before creating a ``SymbolEmbeddingMap``.
-  Assumes a specific directory structure for the storage of the
   embeddings.

Follow-up Questions:
--------------------

-  What are some scenarios where we might need to filter symbols, and
   could these be executed by the provided ``filter_embedding_map``
   method?
-  What are the best practices for managing and storing embeddings for
   large-scale projects with multiple codebases or repositories?
