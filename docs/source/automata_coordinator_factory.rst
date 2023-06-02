AutomataCoordinatorFactory
==========================

``AutomataCoordinatorFactory`` is a class that helps create and
initialize instances of ``AutomataCoordinator``. This factory class
provides a utility method to create ``AutomataCoordinator`` instances
and set up agent-main linkages based on ``AutomataAgentConfig``\ s. It
includes closely related symbols like ``AgentConfigName``,
``AutomataCoordinator``, ``AutomataAgent``, and ``AutomataAgentConfig``.

Overview
--------

``AutomataCoordinatorFactory`` offers a single method,
``create_coordinator``, which takes a main ``AutomataAgent`` and a
dictionary containing ``AutomataAgentConfig``\ s as input. It creates an
instance of ``AutomataCoordinator``, initializes it with the
corresponding ``AutomataInstance``\ s, and sets up a link between the
coordinator and the main agent.

Related Symbols
---------------

-  ``automata.core.coordinator.automata_coordinator.AutomataCoordinator``
-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``

Example
-------

The following example demonstrates how to create an instance of
``AutomataCoordinator`` using ``AutomataCoordinatorFactory`` and a
``main_agent`` instance:

.. code:: python

   from automata.core.coordinator.automata_coordinator_utils import AutomataCoordinatorFactory
   from automata.core.agent.automata_agent import AutomataAgent
   from automata.configs.config_enums import AgentConfigName
   from automata.configs.automata_agent_configs import AutomataAgentConfig

   main_agent = AutomataAgent("Some instructions here.")
   helper_agent_configs = {
       AgentConfigName.AUTOMATA_MAIN_DEV: AutomataAgentConfig.load(AgentConfigName.AUTOMATA_MAIN_DEV),
       AgentConfigName.AUTOMATA_WRITER_DEV: AutomataAgentConfig.load(AgentConfigName.AUTOMATA_WRITER_DEV),
   }

   coordinator = AutomataCoordinatorFactory.create_coordinator(main_agent, helper_agent_configs)

Limitations
-----------

The primary limitation of ``AutomataCoordinatorFactory`` is that it
assumes a specific format and structure for ``AutomataAgentConfig``\ s.
Any changes to this format may require changes to the factory method.

Follow-up Questions:
--------------------

-  How can we improve the creation and management of
   ``AutomataCoordinator`` instances to support different types of agent
   configurations and setups?
-  How can we extend the creation of ``AutomataCoordinator`` instances
   with custom logic and configurations without directly modifying the
   factory method?
