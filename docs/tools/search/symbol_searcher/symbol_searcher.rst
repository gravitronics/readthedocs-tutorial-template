SymbolSearcher
==============

``SymbolSearcher`` is a class that searches for symbols within an
indexed codebase. It provides various search methods, such as exact
search, symbol rank search, and retrieving source code by symbol. The
class also processes NLP-formatted queries to perform the appropriate
search and return the results.

Overview
--------

``SymbolSearcher`` performs searches on the indexed codebase using a
symbol graph, symbol similarity, and symbol rank configurations. The
initialization of the ``SymbolSearcher`` class takes several parameters,
such as ``symbol_graph``, ``symbol_embedding_map``,
``symbol_similarity``, ``symbol_rank_config``, ``code_subgraph``, and
``embedding_dict``. The class supports finding patterns in modules,
processing NLP-based queries, and searching for symbols using various
search methods.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.tool_management.symbol_searcher_manager.SymbolSearcherToolManager``
-  ``automata.tool_management.symbol_searcher_manager.SearchTool``

Example
-------

.. code:: python

   from automata.tools.search.symbol_searcher import SymbolSearcher
   from automata.tools.embedding.symbol_embedding_map import SymbolEmbeddingMap
   from automata.tools.similarity.symbol_similarity import SymbolSimilarity
   from automata.core.graph.symbol_graph import SymbolGraph
   from automata.core.rank.symbol_rank_config import SymbolRankConfig

   # Instantiate required objects
   symbol_graph = SymbolGraph("path/to/index.scip")
   symbol_embedding_map = SymbolEmbeddingMap(
       load_embedding_map=True, embedding_path="path/to/symbol_embedding.json"
   )
   symbol_similarity = SymbolSimilarity(symbol_embedding_map)
   symbol_rank_config = SymbolRankConfig()

   # Create a SymbolSearcher instance
   symbol_searcher = SymbolSearcher(
       symbol_graph, symbol_embedding_map, symbol_similarity, symbol_rank_config
   )

   # Perform an exact search
   exact_search_result = symbol_searcher.exact_search("pattern")

   # Perform a symbol rank search
   symbol_rank_result = symbol_searcher.symbol_rank_search("query")

Limitations
-----------

The functionality of the ``SymbolSearcher`` class is dependent on the
provided ``SymbolGraph``, ``SymbolEmbeddingMap``, ``SymbolSimilarity``,
and ``SymbolRankConfig`` objects. Customizing the behavior of the class
requires modifying these related objects. Additionally, the class
assumes a specific directory structure for the indexed codebase and
might not support custom configurations.

Follow-up Questions:
--------------------

-  Are there possibilities for customizing the behavior of
   ``SymbolSearcher`` beyond the provided related objects?
-  Can we include support for additional search types along with the
   existing ones?
