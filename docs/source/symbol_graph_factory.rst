SymbolGraphFactory
==================

``SymbolGraphFactory`` is a class that creates a ``SymbolGraph`` object,
which represents a graph that captures the relationships between symbols
in a codebase. A ``SymbolGraph`` can be built from an index protobuf
file and used to navigate relationships between different symbols such
as classes, methods, and local variables.

Overview
--------

``SymbolGraphFactory`` provides a way to create a ``SymbolGraph`` object
using the ``create`` method. The method takes an optional ``index_path``
argument, which is a path to the index protobuf file, and an optional
``build_caller_relationships`` boolean argument to enable building
caller relationships between managed functions.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_graph.SymbolGraph``
-  ``automata.core.search.symbol_graph.GraphBuilder``

Example
-------

The following is an example demonstrating how to create an instance of
``SymbolGraph`` using the ``SymbolGraphFactory`` class.

.. code:: python

   from automata.core.search.symbol_factory import SymbolGraphFactory

   # Assuming a valid index protobuf file path
   index_path = "/path/to/index.scip"
   symbol_graph_factory = SymbolGraphFactory()
   symbol_graph = symbol_graph_factory.create(index_path=index_path, build_caller_relationships=True)

Limitations
-----------

-  ``SymbolGraphFactory`` assumes a specific directory structure for the
   configuration files.
-  When creating a ``SymbolGraph`` object, it relies on the index
   protobuf file. Any incorrect or outdated index file might result in
   an inaccurate symbol graph.

Follow-up Questions:
--------------------

-  How can we customize the configuration file directory structure for
   loading the index protobuf file?
