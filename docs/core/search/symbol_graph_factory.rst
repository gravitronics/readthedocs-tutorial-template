SymbolGraphFactory
==================

``SymbolGraphFactory`` is a factory class that is responsible for
creating ``SymbolGraph`` instances. The main purpose of
``SymbolGraphFactory`` is to provide a convenient way to create
``SymbolGraph`` instances without directly specifying all the required
parameters.

Overview
--------

The ``create`` method of ``SymbolGraphFactory`` returns a
``SymbolGraph`` object, which is useful for navigating symbols and their
relationships. The factory class takes care of specifying the default
index path and other required settings for setting up the
``SymbolGraph``.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_graph.SymbolGraph``
-  ``automata.core.search.symbol_graph.GraphBuilder``
-  ``automata.core.code_indexing.python_code_printer.CodePrinter``

Usage Example
-------------

The following example demonstrates how to create an instance of
``SymbolGraph`` using the ``SymbolGraphFactory`` class.

.. code:: python

   from automata.core.search.symbol_factory import SymbolGraphFactory

   factory = SymbolGraphFactory()
   symbol_graph = factory.create()

Limitations
-----------

The primary limitation of ``SymbolGraphFactory`` is that it assumes a
specific structure and default values for configuring the
``SymbolGraph``. Customizing the configuration of ``SymbolGraph`` may
require using ``SymbolGraph`` directly and passing the required
parameters.

Follow-up Questions:
--------------------

-  What is the intended usage of the ``build_caller_relationships``
   parameter in the ``create`` method of ``SymbolGraphFactory``?
-  How can custom index paths be passed to the
   ``SymbolGraphFactory.create()`` method?
