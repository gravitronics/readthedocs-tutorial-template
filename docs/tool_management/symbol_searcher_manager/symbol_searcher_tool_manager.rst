SymbolSearcherToolManager
=========================

``SymbolSearcherToolManager`` is a managing class responsible for
handling symbol search tools such as symbol ranking search, symbol
references, and source code retrieval using the ``SymbolSearcher``
object. It allows users to build, execute, and process symbol search
queries, optionally including post-processing.

Overview
--------

``SymbolSearcherToolManager`` is initialized with a ``SymbolSearcher``
object, a list of search tools, and an optional post-processing
function. Each search operation is represented as a ``Tool`` object,
encapsulating the function to execute for a given search type along with
a name and its description.

The manager provides methods to build search tools and process search
queries according to the specified tool type. It supports a variety of
search operations, such as ranked searching of symbols, finding symbol
references in the codebase, retrieving source code for a symbol, and
performing an exact search for a pattern.

Related Symbols
---------------

-  ``automata.tool_management.tests.test_symbol_searcher_tool_manager.symbol_searcher_tool_builder``
-  ``automata.core.base.tool.Tool``
-  ``automata.tool_management.symbol_searcher_manager.SearchTool``

Example
-------

The following is an example demonstrating how to create an instance of
``SymbolSearcherToolManager`` and process a symbol rank search query.

.. code:: python

   from automata.tool_management.symbol_searcher_manager import SymbolSearcher, SearchTool, SymbolSearcherToolManager

   symbol_searcher = SymbolSearcher()  # Replace with appropriate SymbolSearcher object
   search_tools = [SearchTool.SYMBOL_RANK_SEARCH, SearchTool.SYMBOL_REFERENCES]

   tool_manager = SymbolSearcherToolManager(symbol_searcher=symbol_searcher, search_tools=search_tools)

   query = "query string"  # Replace with appropriate query string
   result = tool_manager.process_query(SearchTool.SYMBOL_RANK_SEARCH, query)
   print(result)

Limitations
-----------

One limitation of the ``SymbolSearcherToolManager`` is that it relies on
the implementations of search operations provided by the underlying
``SymbolSearcher``. If the searcher implementation does not support a
specific search operation, the manager will not be able to execute it.

Another limitation is the use of mock objects in the given context for
testing. These mock objects should ideally be replaced with the actual
underlying objects, but this information is not provided in the current
context.

Follow-up Questions:
--------------------

-  How can users extend the ``SymbolSearcherToolManager`` to incorporate
   custom search operations?
-  Could you provide more information about the ``SymbolSearcher``
   object and its implementation?
