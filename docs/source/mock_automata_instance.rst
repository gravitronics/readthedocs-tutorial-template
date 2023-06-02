Overview
--------

``MockAutomataInstance`` is a mock implementation of
``AutomataInstance`` used for testing purposes. It is designed to
simulate the behavior of an ``AutomataInstance`` without actually
completing a task, making it useful for verifying the functionality of
the ``AutomataCoordinator``.

Related Symbols
---------------

-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.core.coordinator.automata_instance.AutomataInstance``
-  ``automata.core.coordinator.automata_coordinator.AutomataCoordinator``

Example
-------

The following is an example of how to create a ``MockAutomataInstance``
and have it run an instruction. Note that the actual implementation of
the ``MockAutomataInstance`` is simplified for testing purposes and
should not be used in production code.

.. code:: python

   from automata.configs.config_enums import AgentConfigName
   from automata.core.coordinator.tests.test_automata_coordinator import MockAutomataInstance

   config_name = AgentConfigName.AUTOMATA_MAIN_DEV
   description = "Test description"
   mock_instance = MockAutomataInstance(config_name=config_name, description=description)
   instruction = "Test instruction."

   result = mock_instance.run(instruction)
   print(result)  # Output: "Running Test instruction. on automata_main_dev."

Limitations
-----------

``MockAutomataInstance`` is a simplified implementation of
``AutomataInstance`` designed for testing purposes only. It does not
perform actual task execution and should not be used in production code.

Follow-up Questions:
--------------------

-  How do we replace ``MockAutomataInstance`` with the actual underlying
   object in tests?
