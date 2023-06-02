automata.core.agent.automata_agent_utils.AutomataAgentFactory
=============================================================

``AutomataAgentFactory`` is a utility class that provides a method for
creating an instance of ``AutomataAgent`` with the specified
instructions and configurations. It is designed to provide a structured
way to create the agent instances while handling the setup process.

Overview
--------

The main method provided by the ``AutomataAgentFactory`` is the
``create_agent`` method, which takes the instructions and configurations
to be used by the ``AutomataAgent``. The ``create_agent`` method
initializes the agent with the given instructions and configurations,
sets up the agent, and returns the created instance.

Related Symbols
---------------

-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.core.agent.automata_agent_enums.ActionIndicator``
-  ``automata.core.agent.automata_agent_enums.ResultField``
-  ``automata.core.agent.automata_agent.AutomataAgent``

Example
-------

The following is an example demonstrating how to create an instance of
``AutomataAgent`` using the ``AutomataAgentFactory``.

.. code:: python

   from automata.configs.automata_agent_configs import AutomataAgentConfig
   from automata.configs.config_enums import AgentConfigName
   from automata.core.agent.automata_agent_utils import AutomataAgentFactory

   instructions = "Sample instructions for the agent."
   config_name = AgentConfigName.AUTOMATA_MAIN_DEV
   config = AutomataAgentConfig.load(config_name)

   agent = AutomataAgentFactory.create_agent(instructions, config)

Limitations
-----------

The primary limitation of ``AutomataAgentFactory`` is that it only
provides a single method for creating the agent instance, and it assumes
that the setup process is always required. Additionally, the
``create_agent`` method relies on the ``AutomataAgentConfig`` class for
loading the configurations, making it dependent on the limitations of
the config class.

Follow-up Questions:
--------------------

-  Are there any scenarios where we would want to create an agent
   without performing the setup process initially?
-  How can we make the agent creation process more flexible to
   accommodate variations in the setup process?
