SymbolSearcherToolManager
=========================

``SymbolSearcherToolManager`` is a class that manages and builds tools
for symbol searching operations within ``Automata`` codebases. It allows
you to create tools for various search operations such as ranked symbol
search, symbol references, source code retrieval, and exact search. The
class follows a plugin-style architecture, meaning that you can easily
extend and customize the toolbox using its API.

Overview
--------

``SymbolSearcherToolManager`` accepts a ``SymbolSearcher`` object as the
primary input for initializing the tool manager. You can optionally
provide a list of search tools and a post-processing function. The main
methods available are ``build_tool``, ``build_tools``, and
``process_query``. The methods ``build_tool`` and ``build_tools``
generate specific tools or a list of tools, respectively. Meanwhile,
``process_query`` executes searches on symbols by calling the relevant
function, returning the search result or applying a post-processing
function if one is provided.

Related Symbols
---------------

-  ``automata.tool_management.symbol_searcher_manager.SearchTool``
-  ``automata.tools.search.symbol_searcher.SymbolSearcher``
-  ``automata.core.base.tool.Tool``
-  ``automata.core.search.symbol_parser.parse_symbol``
-  ``automata.core.search.symbol_types.Symbol``

Example
-------

In this example, we will show how to create an instance of
``SymbolSearcherToolManager`` and use it to build and process a query
using ``SearchTool.SYMBOL_RANK_SEARCH``.

.. code:: python

   from automata.tool_management.symbol_searcher_manager import (
     SymbolSearcherToolManager,
     SearchTool
   )
   from automata.tools.search.symbol_searcher import SymbolSearcher

   symbol_searcher = SymbolSearcher()
   tool_manager = SymbolSearcherToolManager(symbol_searcher=symbol_searcher)

   # Build tools
   tools = tool_manager.build_tools()

   # Process a ranked symbol search query
   search_type = SearchTool.SYMBOL_RANK_SEARCH
   query = "AutomataAgentConfig"
   ranked_result = tool_manager.process_query(search_type, query)

Limitations
-----------

The primary limitation of ``SymbolSearcherToolManager`` is that it
currently has a hardcoded list of search operations that can be
performed. However, due to its plugin-style architecture, you can extend
and customize this to add more search operation tools.

Follow-up Questions:
--------------------

-  Is it possible to extend ``SymbolSearcherToolManager`` to handle
   additional search functionalities?

(Note: The references to ``Mock`` objects have been removed from the
examples for a better understanding, using the actual underlying
object.)
