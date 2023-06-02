AutomataCoordinator
===================

``AutomataCoordinator`` is a class responsible for managing multiple
``AutomataInstance`` objects. It provides an interface for adding,
removing, and running instances of Automata Agents. The class is
designed to provide an organized management system for coordinating the
execution of different agent instances.

Overview
--------

``AutomataCoordinator`` provides a simple interface for managing
multiple agents. It features methods for adding, removing, and executing
agent instances. It also allows setting a main agent for the
coordinator. The interface allows handling multiple agents
simultaneously, which can be useful in various scenarios such as running
different configurations of the same agent or running multiple, separate
agents.

Related Symbols
---------------

-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.coordinator.automata_instance.AutomataInstance``
-  ``automata.core.agent.automata_actions.AgentAction``

Example
-------

This example demonstrates creating an instance of
``AutomataCoordinator``, adding an ``AutomataInstance`` to it, and
executing an ``AgentAction`` on the instance.

.. code:: python

   from automata.core.agent.automata_actions import AgentAction
   from automata.core.coordinator.automata_instance import AutomataInstance
   from automata.core.agent.automata_agent import AutomataAgent
   from automata.core.coordinator.automata_coordinator import AutomataCoordinator
   from automata.configs.config_enums import AgentConfigName

   coordinator = AutomataCoordinator()

   agent_instance = AutomataInstance(AgentConfigName.DEFAULT)
   coordinator.add_agent_instance(agent_instance)

   action = AgentAction(agent_version=AgentConfigName.DEFAULT, agent_instruction=["Some instruction"])
   result = coordinator.run_agent(action)

   print(result)

Limitations
-----------

The current limitation of ``AutomataCoordinator`` is that it relies on
the existence of a main agent being set. If the main agent is not set,
an error may be encountered when executing agent actions. Additionally,
removal of an ``AutomataInstance`` requires specifying the
``AgentConfigName``, which may not be as intuitive for users when
attempting to remove an agent instance.

Follow-up Questions:
--------------------

-  What is the purpose and usage for the main agent that can be set for
   the ``AutomataCoordinator``?
-  Is there any way to add, remove, or execute agent instances without
   specifying the ``AgentConfigName``?
