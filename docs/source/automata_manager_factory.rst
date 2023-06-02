AutomataManagerFactory
======================

Overview
--------

``AutomataManagerFactory`` is a class responsible for creating
``AutomataManager`` instances. It takes a main agent, an
``AutomataAgent`` instance, and a dictionary of helper agent
configurations keyed on ``AgentConfigName``. The created
``AutomataManager`` manages the interactions between the main agent and
the helper agents, allowing for more nuanced and complex workflows in
executing tasks.

The factory pattern is used to keep the creation of ``AutomataManager``
instances separate and to provide a clean and concise way to create new
instances as needed.

Related Symbols
---------------

-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.core.coordinator.automata_coordinator.AutomataCoordinator``

Example
-------

The following example shows how to create an ``AutomataManager``
instance using ``AutomataManagerFactory``.

.. code:: python

   from automata.core.manager.automata_manager_factory import AutomataManagerFactory
   from automata.core.agent.automata_agent import AutomataAgent
   from automata.configs.automata_agent_configs import AutomataAgentConfig
   from automata.configs.config_enums import AgentConfigName

   # Create a main agent config and instance
   main_agent_config = AutomataAgentConfig.load(AgentConfigName.AUTOMATA_MAIN_DEV)
   main_agent = AutomataAgent("Some instructions", main_agent_config)

   # Create helper agent configs
   helper_agent_configs = {
       AgentConfigName.AUTOMATA_WRITER_DEV: AutomataAgentConfig.load(AgentConfigName.AUTOMATA_WRITER_DEV),
       AgentConfigName.AUTOMATA_INDEXER_DEV: AutomataAgentConfig.load(AgentConfigName.AUTOMATA_INDEXER_DEV)
   }

   # Create an AutomataManager instance using AutomataManagerFactory
   automata_manager = AutomataManagerFactory.create_manager(main_agent, helper_agent_configs)

Limitations
-----------

``AutomataManagerFactory`` relies on the proper configuration of helper
agents and the main agent. If the configurations are incorrect or
incomplete, it may result in errors or unexpected behavior in the
created ``AutomataManager`` instance.

Follow-up Questions:
--------------------

-  How can the creation process be made more robust to handle potential
   issues in agent configurations?
