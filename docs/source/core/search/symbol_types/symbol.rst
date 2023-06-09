Symbol
======

``Symbol`` is similar to a URI (Uniform Resource Identifier) used to
identify a class, method, or a local variable. ``Symbol`` has a
standardized string representation that can be used interchangeably with
a string. It enables representing rich metadata for symbols influenced
by their docstrings.

Overview
--------

The ``Symbol`` class provides representations to identify a class,
method, or a local variable in a structured format. It enables easy
parsing and handling of the Symbol information with various utility
methods. The syntax for ``Symbol`` is standardized and consistent,
allowing it to be used interchangeably with a string. The class allows
for comparisons, hashing, and string representation of Symbols, making
it versatile and useful in various applications.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.SymbolReference``
-  ``automata.core.search.symbol_graph.SymbolGraph``
-  ``automata.core.code_indexing.python_code_printer.CodePrinter``
-  ``automata.core.search.symbol_parser.SymbolParser``
-  ``automata.tools.search.symbol_searcher.SymbolSearcher``
-  ``automata.tool_management.symbol_searcher_manager.SymbolSearcherToolManager``

Example
-------

The following are examples showing how to parse ``Symbol`` and create
instances of the ``Symbol`` class.

.. code:: python

   from automata.core.search.symbol_parser import parse_symbol

   symbol_class = parse_symbol(
     "scip-python python automata 75482692a6fe30c72db516201a6f47d9fb4af065 `automata.core.agent.automata_agent_enums`/ActionIndicator#"
   )

   symbol_method = parse_symbol(
     "scip-python python automata 75482692a6fe30c72db516201a6f47d9fb4af065 `automata.core.base.tool`/ToolNotFoundError#__init__()."
   )

Limitations
-----------

``Symbol`` has a predefined syntax that must be followed to be used
effectively. The class assumes the presence of specific fields like the
package, scheme, or descriptors while parsing the ``Symbol`` strings.
Additionally, the ``Symbol`` class may not be suitable for handling
non-standard or custom URI-like elements.

Follow-up Questions:
--------------------

-  How can we extend the ``Symbol`` class to better support
   customization or non-standard URI-like elements?
