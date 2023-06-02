``AutomataInstance`` Documentation
==================================

Overview
--------

``AutomataInstance`` is a class that represents an instance of an
``AutomataAgent`` and its configuration. It provides a simple interface
to create and run an agent with specified configurations using the
``AutomataAgentConfigFactory`` and ``AutomataAgentFactory``. The class
has a ``run`` method that executes given instructions using the agent
generated from its configuration.

Import Statements
-----------------

.. code:: python

   from typing import Any, Dict
   from pydantic import BaseModel
   from automata.configs.automata_agent_config_utils import AutomataAgentConfigFactory
   from automata.configs.config_enums import AgentConfigName
   from automata.core.agent.automata_agent_utils import AutomataAgentFactory

Related Symbols
---------------

-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.core.coordinator.automata_coordinator.AutomataCoordinator``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``

Example
-------

The following example demonstrates how to create an
``AutomataInstance``, and use it to run given instructions on an agent
generated from its configuration.

.. code:: python

   from automata.core.coordinator.automata_instance import AutomataInstance
   from automata.configs.config_enums import AgentConfigName

   config_name = AgentConfigName.DEFAULT
   description = "AutomataInstance Example"
   instructions = "Test instructions."

   instance = AutomataInstance.create(config_name=config_name, description=description)
   result = instance.run(instructions)

   print(result)

Limitations
-----------

``AutomataInstance`` relies on the predefined configuration files based
on ``AgentConfigName`` and assumes a specific directory structure for
the configuration files. It can only handle agent configurations from
the provided ``AgentConfigName`` enumeration.

Follow-up Questions:
--------------------

-  How can we include custom configuration files for loading into the
   ``AutomataInstance`` class?
