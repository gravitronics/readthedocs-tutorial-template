AutomataAgentConfigFactory
==========================

``AutomataAgentConfigFactory`` is a utility class that provides a
convenient way to create instances of ``AutomataAgentConfig`` with
custom configurations. It includes a static method ``create_config``
that takes various optional parameters and constructs an appropriate
``AutomataAgentConfig`` instance.

Overview
--------

The ``AutomataAgentConfigFactory`` method ``create_config`` can be used
to create customized ``AutomataAgentConfig`` objects by providing
arguments such as ``main_config_name``, ``main_config``, and various
other configurations. It simplifies the creation of custom agent
configurations and ensures that all required setups are handled
efficiently.

Related Symbols
---------------

-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.automata_agent_config_utils.AutomataAgentConfigBuilder``
-  ``automata.core.coordinator.automata_instance.AutomataInstance``

Example
-------

Below is an example demonstrating how to use
``AutomataAgentConfigFactory`` to create an ``AutomataAgentConfig``
object with custom configurations.

.. code:: python

   from automata.configs.config_enums import AgentConfigName
   from automata.configs.automata_agent_config_utils import AutomataAgentConfigFactory

   main_config_name = AgentConfigName.AUTOMATA_MAIN_DEV
   instruction_payload = {
       "agents_message": "This is an example",
   }
   model = "gpt-4"
   session_id = "example-session"

   config = AutomataAgentConfigFactory.create_config(
       main_config_name=main_config_name,
       instruction_payload=instruction_payload,
       model=model,
       session_id=session_id
   )

Limitations
-----------

``AutomataAgentConfigFactory`` assumes that all configurations are
provided using the appropriate arguments. Invalid configurations or
missing arguments can lead to errors during the creation of an
``AutomataAgentConfig`` object.

Follow-up Questions:
--------------------

-  Can we pass custom configuration files to
   ``AutomataAgentConfigFactory``?
