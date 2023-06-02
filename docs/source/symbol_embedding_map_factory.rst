SymbolEmbeddingMapFactory
=========================

``SymbolEmbeddingMapFactory`` is a factory class that creates instances
of ``SymbolEmbeddingMap``. It is a simple factory, containing a single
``create`` method.

Overview
--------

``SymbolEmbeddingMapFactory`` provides a way to create instances of
``SymbolEmbeddingMap``. This factory class is useful when you need to
create instances of ``SymbolEmbeddingMap`` in a flexible and concise
manner, without directly calling the constructor of
``SymbolEmbeddingMap``.

Related Symbols
---------------

-  ``automata.core.search.symbol_rank.symbol_embedding_map.SymbolEmbeddingMap``
-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_types.SymbolEmbedding``
-  ``automata.core.search.symbol_factory.SymbolSimilarityFactory``
-  ``automata.core.search.symbol_rank.symbol_similarity.SymbolSimilarity``

Example
-------

The following is an example demonstrating how to create an instance of
``SymbolEmbeddingMap`` using the ``SymbolEmbeddingMapFactory``.

.. code:: python

   from automata.core.search.symbol_factory import SymbolEmbeddingMapFactory
   from automata.core.search.symbol_rank.symbol_embedding_map import SymbolEmbeddingMap

   factory = SymbolEmbeddingMapFactory()
   symbol_embedding_map = factory.create(all_defined_symbols=[...])

Limitations
-----------

``SymbolEmbeddingMapFactory`` is a very simple factory class, and its
primary limitation is that it only supports creating instances of
``SymbolEmbeddingMap``. Additionally, it is necessary to provide a list
of all defined symbols when creating a new ``SymbolEmbeddingMap``
instance. There might be scenarios where it’s difficult to provide such
a list, and in these cases, the factory could be less useful.

Follow-up Questions:
--------------------

-  Are there alternative ways to create instances of
   ``SymbolEmbeddingMap``, other than using
   ``SymbolEmbeddingMapFactory``?
-  Can the ``SymbolEmbeddingMapFactory`` be extended to support other
   types of objects in addition to ``SymbolEmbeddingMap``?
