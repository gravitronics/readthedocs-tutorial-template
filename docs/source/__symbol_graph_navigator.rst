Overview
========

``_SymbolGraphNavigator`` is a class that handles navigation of a symbol
graph. It provides various methods to explore defined symbols, files,
symbol callers, symbol callees, symbol references, symbol dependencies,
and symbol relationships in the graph. The class requires a ``graph``
object of type ``nx.MultiDiGraph`` during instantiation.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_graph.SymbolGraph``
-  ``automata.core.code_indexing.python_code_printer.CodePrinter``
-  ``automata.core.search.symbol_graph.GraphBuilder``
-  ``automata.tools.search.symbol_searcher.SymbolSearcher``
-  ``automata.core.search.symbol_parser.SymbolParser``
-  ``automata.tool_management.symbol_searcher_manager.SymbolSearcherToolManager``

Example
-------

The following example demonstrates how to use ``_SymbolGraphNavigator``
to navigate a symbol graph.

.. code:: python

   import networkx as nx
   from automata.core.search.symbol_graph import _SymbolGraphNavigator

   # Create a sample MultiDiGraph
   graph = nx.MultiDiGraph()

   # Add some sample data to the graph (example purpose only)
   graph.add_node(1, label="symbol")
   graph.add_node(2, label="file")
   graph.add_node(3, label="callee")
   graph.add_edges_from([(1, 3, {"label": "caller"})])

   # Instantiate _SymbolGraphNavigator with the graph
   navigator = _SymbolGraphNavigator(graph)

   # Get all defined symbols in the graph
   defined_symbols = navigator.get_all_defined_symbols()
   print(defined_symbols)  # Output: [1]

   # Get all files in the graph
   files = navigator.get_all_files()
   print(files)  # Output: [2]

   # Get potential symbol callees
   callees = navigator.get_potential_symbol_callees(1)
   print(callees)  # Output: {3: SymbolReference(...}

   # Get potential symbol callers
   callers = navigator.get_potential_symbol_callers(3)
   print(callers)  # Output: {SymbolReference(...: 1}

Limitations
-----------

The ``_SymbolGraphNavigator`` class requires the input graph to be
correctly constructed and have appropriate data before performing
navigations. If the graph is not appropriately organized, it may return
incorrect results or raise exceptions.

Follow-up Questions:
--------------------

-  How does the graph structure affect the performance and accuracy of
   the navigator class?
