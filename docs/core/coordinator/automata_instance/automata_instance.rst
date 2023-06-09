AutomataInstance
================

``AutomataInstance`` is a class that creates and manages instances of
Automata agents. It provides methods for initializing an instance with
various configuration options and running instructions on the configured
agent. The class works closely with other components of the Automata
ecosystem like ``AutomataAgent``, ``AutomataAgentConfig``, and
``AutomataCoordinator``.

Overview
--------

``AutomataInstance`` offers a convenient way to create and manage an
instance of an agent with custom configurations. Instances can be
created using the provided ``create`` method and a set of configuration
options. The ``run`` method allows executing instructions on the agent
and retrieving generated outputs.

Related Symbols
---------------

-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.core.coordinator.automata_coordinator.AutomataCoordinator``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``

Example
-------

The following is an example demonstrating how to create an instance of
``AutomataInstance`` and run a set of instructions on it:

.. code:: python

   from automata.core.coordinator.automata_instance import AutomataInstance
   from automata.configs.config_enums import AgentConfigName

   config_name = AgentConfigName.AUTOMATA_MAIN_DEV
   description = "Automata Main Development Instance"
   instance = AutomataInstance.create(config_name=config_name, description=description)

   instructions = "Hello, world!"
   output = instance.run(instructions)
   print("Agent Output:", output)

Limitations
-----------

The primary limitation of ``AutomataInstance`` is its dependency on the
predefined configuration files based on ``AgentConfigName``. It can only
use configurations from those files and cannot load custom configuration
files. Additionally, it requires a specific directory structure for the
configuration files.

Follow-up Questions:
--------------------

-  Can we introduce a way to include custom configuration files for
   loading into ``AutomataInstance``?
