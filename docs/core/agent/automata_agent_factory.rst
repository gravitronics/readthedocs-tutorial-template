automata.core.agent.automata_agent_utils.AutomataAgentFactory
=============================================================

``AutomataAgentFactory`` is a factory class used to create an instance
of ``AutomataAgent``. The main method offered by this class is
``create_agent``, which creates an agent with given instructions and
optional configurations.

Overview
--------

``AutomataAgentFactory`` provides a convenient and straightforward way
to create an instance of ``AutomataAgent`` while abstracting away the
agent setup logic. This allows for a seamless process while initializing
an agent to execute instructions and report the results back to the main
system. The factory class also works in conjunction with related symbols
like ``AutomataAgentConfig``, ``AgentConfigName``, and the
``AutomataAgent`` itself.

Related Symbols
---------------

-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.configs.automata_agent_config_utils.AutomataAgentConfigBuilder``

Example
-------

The following is an example demonstrating how to create an instance of
``AutomataAgent`` using ``AutomataAgentFactory``.

.. code:: python

   from automata.core.agent.automata_agent_utils import AutomataAgentFactory
   from automata.configs.automata_agent_configs import AutomataAgentConfigBuilder
   from automata.configs.config_enums import AgentConfigName

   instructions = "Test instruction."
   config_name = AgentConfigName.AUTOMATA_MAIN_DEV
   config = AutomataAgentConfigBuilder.from_name(config_name).build()

   agent = AutomataAgentFactory.create_agent(instructions=instructions, config=config)

Limitations
-----------

The primary limitation of ``AutomataAgentFactory`` is that it relies on
the ``AutomataAgent`` and its configurations to create an agent
instance. Customizations for creating an agent would require the user to
work closely with the ``AutomataAgentConfig`` and the
``AutomataAgentConfigBuilder`` classes, as well as adhering to the
expected directory structure for configuration files.

Follow-up Questions:
--------------------

-  What are the specific directory structures required for configuration
   files used by ``AutomataAgentFactory``?
-  Are there any plans to support customizations beyond the provided
   configuration options in the future?
