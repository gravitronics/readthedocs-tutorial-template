AutomataCoordinatorFactory
==========================

The ``AutomataCoordinatorFactory`` class provides a utility method for
creating an ``AutomataCoordinator`` and setting up its agent-main
linkage. It is used to initialize an ``AutomataAgent`` instance and a
list of ``AutomataAgentConfig`` instances to create an
``AutomataCoordinator`` for managing ``AutomataInstance`` objects.

Overview
--------

The ``create_coordinator`` static method in
``AutomataCoordinatorFactory`` is responsible for creating an
``AutomataCoordinator`` instance and adding ``AutomataInstance`` objects
for each given ``AutomataAgentConfig``. The main agent is then linked to
the coordinator, and the created ``AutomataCoordinator`` instance is
returned.

Related Symbols
---------------

-  ``automata.core.coordinator.automata_coordinator.AutomataCoordinator``
-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.core.coordinator.automata_instance.AutomataInstance``

Example
-------

The following example demonstrates how to create an
``AutomataCoordinator`` using the ``AutomataCoordinatorFactory``.

.. code:: python

   from automata.core.agent.automata_agent import AutomataAgent
   from automata.core.coordinator.automata_coordinator_utils import AutomataCoordinatorFactory
   from automata.configs.config_enums import AgentConfigName
   from automata.configs.automata_agent_configs import AutomataAgentConfig

   main_agent = AutomataAgent("Example instruction")
   helper_agent_configs = {
       AgentConfigName.AUTOMATA_WRITER_DEV: AutomataAgentConfig.load(AgentConfigName.AUTOMATA_WRITER_DEV)
   }

   coordinator = AutomataCoordinatorFactory.create_coordinator(main_agent, helper_agent_configs)

Limitations
-----------

The primary limitation of the ``AutomataCoordinatorFactory`` is that it
requires users to create and provide instances of ``AutomataAgent`` and
``AutomataAgentConfig``. This might not be suitable for all use cases or
might require additional setup or customization.

Follow-up Questions:
--------------------

-  Is there a more user-friendly way for creating an
   ``AutomataCoordinator`` without the need for the factory?
-  Can the factory also support automatically creating the main agent if
   required?
