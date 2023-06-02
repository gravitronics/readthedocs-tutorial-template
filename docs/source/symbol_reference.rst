SymbolReference
===============

``SymbolReference`` is a data class that represents a reference to a
specific symbol. It keeps track of the symbol, the line number, and the
column number where the symbol is referenced. The class contains methods
for comparison and generating hash of the object, making it helpful in
identifying and comparing references in a clean and orderly fashion.

Overview
--------

A ``SymbolReference`` stores the following information:

-  The symbol being referenced (an instance of
   ``automata.core.search.symbol_types.Symbol``)
-  The line number of the reference
-  The column number of the reference

``SymbolReference`` provides methods for comparing and hashing the
object, allowing it to be used effectively in tracking symbol references
and their occurrences in source code.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_graph.SymbolGraph``
-  ``automata.core.code_indexing.python_code_printer.CodePrinter``
-  ``automata.core.search.symbol_types.Descriptor``

Example
-------

Below is an example of how to create a ``SymbolReference`` and compare
it with another ``SymbolReference``.

.. code:: python

   from automata.core.search.symbol_types import Symbol, SymbolReference

   symbol1 = Symbol(scheme="scip-python",
                   manager="python",
                   package_name="automata",
                   version="75482692a6fe30c72db516201a6f47d9fb4af065",
                   descriptor="`automata.core.agent.automata_agent_enums`/ActionIndicator#")

   symbol2 = Symbol(scheme="scip-python",
                   manager="python",
                   package_name="automata",
                   version="75482692a6fe30c72db516201a6f47d9fb4af065",
                   descriptor="`automata.core.base.tool`/ToolNotFoundError#__init__().")

   reference1 = SymbolReference(symbol=symbol1, line_number=10, column_number=5)
   reference2 = SymbolReference(symbol=symbol2, line_number=20, column_number=15)

   # Compare references
   print(reference1 == reference2)  # Output: False

   # Hash references
   print(hash(reference1))
   print(hash(reference2))

Limitations
-----------

The primary limitation of the ``SymbolReference`` is that it could cause
collisions if the same symbol is referenced in different files at the
same location. This is because the hash method only takes into account
the symbol’s URI and the line and column number where it is referenced.

Follow-up Questions:
--------------------

-  Can a more sophisticated hashing method be employed to avoid
   collision issues?
