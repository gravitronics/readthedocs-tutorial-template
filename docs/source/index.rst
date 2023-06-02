Welcome to Lumache's documentation!
===================================

**Lumache** (/lu'make/) is a Python library for cooks and food lovers
that creates recipes mixing random ingredients.
It pulls data from the `Open Food Facts database <https://world.openfoodfacts.org/>`_
and offers a *simple* and *intuitive* API.

Check out the :doc:`usage` section for further information, including
how to :ref:`installation` the project.

.. note::

   This project is under active development. ~~test~~
Symbol
======

``Symbol`` is a class that represents a unified resource identifier
(URI) for identifying classes, methods, or local variables in a
codebase. It stores rich metadata about symbols, such as their
docstrings.

The standardized string representation of a ``Symbol`` can be used
interchangeably with the object itself. The syntax for a ``Symbol`` is
complex and defined in the class docstring.

Overview
--------

``Symbol`` helps in uniquely identifying various elements of a codebase,
like classes, methods, and variables. It provides utility methods for
dealing with Symbols, such as comparing equality, finding parents, and
checking the kind of a symbol. ``Symbol`` can be created from a string
using the ``from_string`` method or using the ``parse_symbol`` function
from ``symbol_parser``.

Related Symbols
---------------

-  ``automata.core.search.symbol_parser.SymbolParser``
-  ``automata.core.search.symbol_graph.SymbolGraph``
-  ``automata.core.search.symbol_types.SymbolReference``
-  ``automata.tool_management.symbol_searcher_manager.SymbolSearcherToolManager``
-  ``automata.core.search.symbol_rank.symbol_embedding_map.SymbolEmbeddingMap``

Examples
--------

Assuming you have the following symbols:

.. code:: python

   symbol_class = parse_symbol("scip-python python automata 75482692a6fe30c72db516201a6f47d9fb4af065 `automata.core.agent.automata_agent_enums`/ActionIndicator#")

   symbol_method = parse_symbol("scip-python python automata 75482692a6fe30c72db516201a6f47d9fb4af065 `automata.core.base.tool`/ToolNotFoundError#__init__().")

You can check if a symbol is local, meta, or parameter using the
following functions:

.. code:: python

   if Symbol.is_local(symbol_class):
       print("symbol_class is local")

   if Symbol.is_meta(symbol_class):
       print("symbol_class is meta")

   if Symbol.is_parameter(symbol_class):
       print("symbol_class is parameter")

Limitations
-----------

As of its current implementation, ``Symbol`` can only handle specific
syntax defined in the class docstring, which might not be sufficient for
all use cases. Modifying the syntax to include additional features would
require changes in the source code. Additionally, the class relies on
various external tools and libraries which might introduce further
limitations.

Follow-up Questions:
--------------------

-  Are there any plans to support custom syntax or extend the
   capabilities of ``Symbol`` in the future?
-  How can we improve the handling of potential limitations related to
   external tools and libraries?


.. toctree::

   usage
   api
