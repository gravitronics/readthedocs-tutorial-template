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
   
# Symbol Reference

## Overview

The `SymbolReference` class represents the instance of a reference to a symbol, including which file the reference appears in and the position (line number and column number) of the reference. It also defines how to check for equality and hash the SymbolReference.

The `SymbolReference` class is part of the `automata.core.search.symbol_types` package, which contains various classes and methods related to symbol handling, such as Symbol, Descriptor, and Package.

## Related Symbols

**automata.core.search.symbol_types.Symbol**

  - Main class to represent a symbol, which contains the name, type, and characteristics of a symbol.

**automata.core.code_indexing.python_code_printer.CodePrinter**

  - Modules and classes for navigating and printing the code related to a symbol.

**automata.core.search.symbol_types.Descriptor**

  - Descriptor class is responsible for the descriptor data of a symbol, such as the name, type, and representation.

**automata.core.search.symbol_parser.SymbolParser**

  - SymbolParser class is used for parsing a string representation of a symbol into a Symbol object.

**automata.core.search.symbol_graph.SymbolGraph**

  - SymbolGraph class represents and navigates symbol relationships and dependencies in a codebase.

## Examples

### Comparing Two Symbol References

```python
symbol_ref1 = SymbolReference(symbol=my_symbol, file=my_file, line_number=2, column_number=8)
symbol_ref2 = SymbolReference(symbol=my_symbol2, file=my_file, line_number=2, column_number=8)

# Check if references are equal
if symbol_ref1 == symbol_ref2:
    print("Symbol references are equal!")
else:
    print("Symbol references are different!")
```

### Getting the Hash of a Symbol Reference

```python
symbol_ref1 = SymbolReference(symbol=my_symbol, file=my_file, line_number=2, column_number=8)

# Get the hash of the symbol_ref1
hash_symbol_ref1 = hash(symbol_ref1)
print(f"Hash of symbol_ref1 is {hash_symbol_ref1}.")
```

## Limitations

- The `__hash__` method may generate collisions if the same symbol is referenced in different files at the same location. This can lead to incorrect comparison results when using the `__eq__` method.
   

Contents
--------

.. toctree::

   usage
   api
