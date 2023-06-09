SymbolGraph
===========

``SymbolGraph`` is a data structure representation of a codebase used in
Automata. It is built from an index protobuf file and provides methods
to query and analyze code elements such as symbols, files, and
relationships between code elements. The class allows users to query the
codebase by symbol, file, and relationships like callers and callees,
and it returns relevant elements such as symbols, files, and symbol
references.

Overview
--------

The ``SymbolGraph`` class is initialized with the path to an index
protobuf file and optionally the ``build_caller_relationships`` flag. It
provides methods like ``get_all_defined_symbols()``,
``get_all_files()``, ``get_potential_symbol_callees()``,
``get_potential_symbol_callers()``, ``get_rankable_symbol_subgraph()``,
``get_references_to_symbol()``, ``get_symbol_dependencies()``, and
``get_symbol_relationships()`` that allow users to perform various
queries and analyses on the codebase.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.code_indexing.python_code_printer.CodePrinter``
-  ``automata.core.search.symbol_graph.GraphBuilder``
-  ``automata.core.search.symbol_types.SymbolReference``
-  ``automata.tools.search.symbol_searcher.SymbolSearcher``
-  ``automata.core.search.symbol_rank.symbol_rank.SymbolRank``
-  ``automata.core.search.symbol_rank.symbol_embedding_map.SymbolEmbeddingMap``

Example
-------

The following is an example demonstrating how to create an instance of
``SymbolGraph`` using a path to an index protobuf file and query for all
defined symbols in the codebase.

.. code:: python

   from automata.core.search.symbol_graph import SymbolGraph

   index_path = "/path/to/index.protobuf"
   symbol_graph = SymbolGraph(index_path)
   all_defined_symbols = symbol_graph.get_all_defined_symbols()

Limitations
-----------

The ``SymbolGraph`` relies on an index protobuf file for building the
graph. This protobuf file must be generated beforehand, and the path to
it must be provided during initialization. Furthermore, the graph’s
analysis and query capabilities may be limited by the quality and
completeness of the index file.

Follow-up Questions:
--------------------

-  How can we generate the index protobuf file used for initializing a
   ``SymbolGraph``?
-  Are there any limitations in querying or analyzing the codebase using
   ``SymbolGraph``?
