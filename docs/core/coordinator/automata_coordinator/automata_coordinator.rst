AutomataCoordinator
===================

``AutomataCoordinator`` is a class responsible for managing multiple
``AutomataInstance`` objects. It helps coordinate the execution of
actions on their agent instances, add or remove agent instances, and set
the main agent for the coordinator.

Overview
--------

The main functionality of the ``AutomataCoordinator`` class is to manage
multiple ``AutomataInstance`` objects, allowing various agent instances
to be added or removed from the coordinator. It provides methods to
execute specified actions on the agent instances and returns their
output. The class is designed to be used alongside other classes such as
``AutomataAgent`` and ``AutomataInstance``.

Related Symbols
---------------

-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.coordinator.automata_instance.AutomataInstance``

Example
-------

The following is an example demonstrating how to create an instance of
``AutomataCoordinator`` and add an agent instance to it.

.. code:: python

   from automata.core.coordinator.automata_coordinator import AutomataCoordinator
   from automata.core.agent.automata_agent import AutomataAgent
   from automata.configs.automata_agent_configs import AutomataAgentConfig
   from automata.core.coordinator.automata_instance import AutomataInstance
   from automata.configs.config_enums import AgentConfigName

   # Create an AutomataCoordinator instance
   coordinator = AutomataCoordinator()

   # Create an AutomataAgentConfig instance with the desired configuration name
   agent_config = AutomataAgentConfig.load(AgentConfigName.AUTOMATA_MAIN_DEV)

   # Create an AutomataAgent instance with the specified instructions and config
   agent_instance = AutomataAgent("Some instructions for the agent.", agent_config)

   # Create an AutomataInstance and add it to the coordinator
   automata_instance = AutomataInstance(agent_instance, config_name=AgentConfigName.AUTOMATA_MAIN_DEV)
   coordinator.add_agent_instance(automata_instance)

Limitations
-----------

In its current implementation, ``AutomataCoordinator`` could be limited
in its ability to handle a large number of agent instances or handle
concurrency efficiently. Additionally, the approach to adding and
removing instances by checking their ``config_name`` could be a source
of potential errors if multiple instances with the same names are being
managed.

Follow-up Questions:
--------------------

-  Are there better ways to handle the management of multiple agent
   instances to improve performance and error handling?
