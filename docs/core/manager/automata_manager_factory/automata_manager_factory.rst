automata.core.manager.automata_manager_factory.AutomataManagerFactory
=====================================================================

``AutomataManagerFactory`` is a class for creating ``AutomataManager``
instances.

Overview
--------

``AutomataManagerFactory`` provides a static method called
``create_manager``. It is responsible for creating an
``AutomataManager`` instance from a given main agent (``AutomataAgent``)
and a dictionary of helper agent configurations
(``AutomataAgentConfig``), keyed on ``AgentConfigName``. The factory
creates an ``AutomataCoordinator`` using the main agent and helper agent
configurations and returns an ``AutomataManager`` instance with the main
agent and the coordinator.

Related Symbols
---------------

-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.core.coordinator.automata_coordinator.AutomataCoordinator``

Example
-------

The following is an example demonstrating how to create an instance of
``AutomataManager`` using ``AutomataManagerFactory``.

.. code:: python

   from automata.core.manager.automata_manager_factory import AutomataManagerFactory
   from automata.core.agent.automata_agent import AutomataAgent
   from automata.configs.automata_agent_configs import AutomataAgentConfig
   from automata.configs.config_enums import AgentConfigName

   main_agent = AutomataAgent("Some instructions")
   helper_agent_configs = {
       AgentConfigName.AUTOMATA_WRITER_DEV: AutomataAgentConfig.load(AgentConfigName.AUTOMATA_WRITER_DEV)
   }

   manager = AutomataManagerFactory.create_manager(main_agent, helper_agent_configs)

Limitations
-----------

The main limitation of ``AutomataManagerFactory`` is that it only
supports creating an ``AutomataManager`` with a given set of helper
agent configurations, specified using ``AgentConfigName``. If custom
configuration files or a different structure are desired for the helper
agents, additional work would be required.

Follow-up Questions
-------------------

-  How can we include custom configurations or additional agents in the
   factory’s creation process?
