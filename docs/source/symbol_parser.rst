SymbolParser
============

``SymbolParser`` is a class that provides functions to parse URIs
(Uniform Resource Identifiers) into structured objects. It is a
translation of the logic defined in the Go implementation at
`Sourcegraph
SCIP <https://github.com/sourcegraph/scip/blob/ee677ba3756cdcdb55b39942b5701f0fde9d69fa/bindings/go/scip/symbol.go>`__.
The benefit of using this class is parsing more complex URIs into
useful, structured data, making it easier to work with symbol-related
data.

While it is not in hard sync with the Go implementation, it is
sufficient for most use cases. Parsed URIs will be returned as a
``Symbol``.

Related Symbols
---------------

-  ``automata.core.search.symbol_types.Symbol``
-  ``automata.core.search.symbol_types.Package``
-  ``automata.core.search.symbol_types.Descriptor``
-  ``automata.core.search.symbol_parser.SymbolParser``

Example
-------

In this example, we will demonstrate how to parse a ``Symbol`` with
``SymbolParser``.

.. code:: python

   from automata.core.search.symbol_parser import SymbolParser
   from automata.core.search.symbol_types import Symbol

   uri = "scip-python python automata 75482692a6fe30c72db516201a6f47d9fb4af065 `automata.core.agent.automata_agent_enums`/ActionIndicator#"
   symbol_parser = SymbolParser(uri)
   parsed_symbol = Symbol(
       scheme="scip-python",
       package=Package("python", "automata", "75482692a6fe30c72db516201a6f47d9fb4af065"),
       descriptors=symbol_parser.parse_descriptors(),
   )

Limitations
-----------

As mentioned earlier, ``SymbolParser`` is not in hard sync with the Go
implementation. As such, if there are updates to the original
implementation, it may not cover all the possible cases and
functionalities provided by the Go version. However, it is sufficient
for most use cases and can be easily modified to cover any additional
functionality needed.

Follow-up Questions
-------------------

-  Are there any plans to keep the implementation in sync with the Go
   version?
-  How can a user modify the ``SymbolParser`` to add more functionality
   or cover additional use cases if needed?
