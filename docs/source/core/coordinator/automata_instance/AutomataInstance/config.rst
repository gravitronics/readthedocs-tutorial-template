automata.core.coordinator.automata_instance.AutomataInstance.Config
===================================================================

``AutomataInstance.Config`` is a configuration class specifically
designed for ``AutomataInstance`` derived classes, providing a way to
define and manage their configurations when instantiated by the
``AutomataCoordinator``. This configuration class allows
``AutomataInstance`` to load predefined ``AgentConfigName``\ s with
optional parameters like ``arbitrary_types_allowed`` to provide greater
flexibility during an instance setup and execution.

Related Symbols
---------------

-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.core.coordinator.automata_coordinator.AutomataCoordinator``
-  ``automata.core.coordinator.automata_instance.AutomataInstance``

Example
-------

The following is an example demonstrating how to create an instance of
``AutomataInstance`` with a custom ``AutomataInstance.Config``.

.. code:: python

   from automata.core.coordinator.automata_instance import AutomataInstance
   from automata.configs.config_enums import AgentConfigName

   class CustomAutomataInstance(AutomataInstance):
       def __init__(
           self,
           config_name: AgentConfigName,
           description: str,
       ):
           super().__init__(config_name=config_name, description=description)

   config_name = AgentConfigName.AUTOMATA_MAIN_DEV
   description = "This is a custom AutomataInstance."

   custom_instance = CustomAutomataInstance(config_name=config_name, description=description)

Limitations
-----------

As ``AutomataInstance.Config`` is specifically designed for
``AutomataInstance``, it cannot be used as a standalone configuration
class for other purposes. Additionally, the available configurations are
limited to those defined within the ``AgentConfigName`` enumeration,
which may not cover all possible use cases.

Follow-up Questions:
--------------------

-  Can the ``AutomataInstance.Config`` class be extended for greater
   customization?
-  Is there a way to integrate custom configuration files in the
   ``AutomataInstance.Config`` class?
