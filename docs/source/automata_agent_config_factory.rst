AutomataAgentConfigFactory
==========================

``AutomataAgentConfigFactory`` is a utility class that offers a static
method ``create_config`` to create instances of ``AutomataAgentConfig``
with the provided arguments and configurations. It simplifies the
process of creating, configuring, and setting up an
``AutomataAgentConfig`` object for various use cases.

Overview
--------

The factory class allows users to create instances of
``AutomataAgentConfig`` easily with custom configurations, either by
passing a predefined ``AgentConfigName`` or an existing
``AutomataAgentConfig`` object. The factory’s ``create_config`` method
offers a flexible way to pass in additional configurations, tools,
models, and settings as keyword arguments, providing a simple interface
for setting up a customized agent configuration.

Related Symbols
---------------

-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.configs.automata_agent_config_utils.AutomataAgentConfigBuilder``
-  ``automata.core.base.tool.Toolkit``
-  ``automata.core.agent.automata_agent.AutomataAgent``

Example
-------

The following is an example demonstrating how to create an instance of
``AutomataAgentConfig`` using
``AutomataAgentConfigFactory.create_config()`` method.

.. code:: python

   from automata.configs.automata_agent_config_utils import AutomataAgentConfigFactory
   from automata.configs.config_enums import AgentConfigName

   main_config_name = AgentConfigName.AUTOMATA_MAIN_DEV
   config = AutomataAgentConfigFactory.create_config(main_config_name=main_config_name, model="gpt-4")

Limitations
-----------

The primary limitation of ``AutomataAgentConfigFactory`` is that it only
supports creating ``AutomataAgentConfig`` instances with the
configurations and settings that are supported by the underlying
``AutomataAgentConfig`` class. It does not support loading custom
configuration files or creating entirely new configuration options that
are not already defined within the related classes.

Follow-up Questions:
--------------------

-  Is there a way to extend the ``AutomataAgentConfigFactory`` to
   support custom configuration settings?
-  How can we include custom configuration files for loading into the
   ``AutomataAgentConfigFactory`` class?
