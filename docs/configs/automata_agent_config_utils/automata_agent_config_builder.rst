AutomataAgentConfigBuilder
==========================

The ``AutomataAgentConfigBuilder`` class provides a flexible and
easy-to-use interface for constructing instances of ``AutomataAgent``.
You can set various properties, such as ``model``, ``stream``,
``max_iters``, and ``instruction_version``, before instantiating an
``AutomataAgent``.

Overview
--------

``AutomataAgentConfigBuilder`` is designed to allow users to easily
update and modify agent configuration settings. It provides methods for
building an ``AutomataAgentConfig`` instance with custom configurations
by chaining methods together.

The resulting configuration object can then be used to initialize the
``AutomataAgent`` instance.

Example
-------

.. code:: python

   from automata.configs.automata_agent_configs import AutomataAgentConfig
   from automata.configs.automata_agent_config_utils import AutomataAgentConfigBuilder

   config = (
       AutomataAgentConfigBuilder()
       .with_model("gpt-4")
       .with_stream(True)
       .with_max_iters(50)
       .with_instruction_version("1.0")
       .build()
   )

   agent = AutomataAgent(
       instructions="Write a brief summary of the article about machine learning.",
       config=config
   )

Methods
-------

build()
~~~~~~~

This method builds and returns an ``AutomataAgentConfig`` instance with
the current configuration.

.. code:: python

   config = AutomataAgentConfigBuilder().with_model("gpt-4").build()

from_config(config)
~~~~~~~~~~~~~~~~~~~

This class method creates an ``AutomataAgentConfigBuilder`` instance
using the provided ``AutomataAgentConfig`` object.

.. code:: python

   another_config = AutomataAgentConfigBuilder.from_config(config)

with\_\* methods
~~~~~~~~~~~~~~~~

These methods help set various properties for the ``AutomataAgent``
instance, such as ``model``, ``stream``, ``max_iters``, and more. They
return the current ``AutomataAgentConfigBuilder`` instance with the
updated property values, which allows for easy method chaining.

.. code:: python

   config = (
       AutomataAgentConfigBuilder()
       .with_model("gpt-4")
       .with_stream(True)
       .with_max_iters(50)
       .with_instruction_version("1.0")
       .build()
   )

Limitations
-----------

The primary limitation of the ``AutomataAgentConfigBuilder`` is that it
only supports building ``AutomataAgentConfig`` instances, and it may be
necessary to update the builder if new configuration options become
available or if some options are deprecated.

Follow-up Questions:
--------------------

-  How can we extend the builder to accommodate new configuration
   options or settings?
