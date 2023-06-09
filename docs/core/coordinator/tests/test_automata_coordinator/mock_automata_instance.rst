MockAutomataInstance
====================

``MockAutomataInstance`` is a mock class created primarily for testing
purposes to replace the actual underlying ``AutomataInstance`` object.
It is used to simplify working with complex objects during testing while
still allowing the proper execution of tests.

Overview
--------

``MockAutomataInstance`` can be initialized with a ``config_name``,
which is an instance of the ``AgentConfigName`` enum, and a
``description``. The class defines a ``run()`` method which accepts an
``instruction`` argument and returns a formatted string with the
selected configuration and provided instruction.

As this is a mock class, it should generally not be used in the main
codebase. Instead, refer to the ``AutomataInstance`` class and its
related symbols.

Related Symbols
---------------

-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.core.coordinator.automata_instance.AutomataInstance``
-  ``automata.core.coordinator.automata_coordinator.AutomataCoordinator``

Example
-------

The following is an example demonstrating how to create an instance of
``MockAutomataInstance`` for testing purposes.

.. code:: python

   from automata.core.coordinator.tests.test_automata_coordinator import MockAutomataInstance
   from automata.configs.config_enums import AgentConfigName

   config_name = AgentConfigName.TEST
   description = "Mock agent for testing."
   mock_instance = MockAutomataInstance(config_name=config_name, description=description)

   instruction = "Test instruction."
   response = mock_instance.run(instruction)
   print(response)  # Output: Running Test instruction on test.

Limitations
-----------

``MockAutomataInstance`` is not intended for use in the main codebase as
it is a mock object created for testing purposes. Further, due to its
simplified nature, it might not cover all possible behaviors and
interactions of a real ``AutomataInstance``.

Follow-up Questions:
--------------------

-  What are the key differences between ``MockAutomataInstance`` and the
   actual ``AutomataInstance`` class?
-  In what scenarios should ``MockAutomataInstance`` be used instead of
   ``AutomataInstance``?
