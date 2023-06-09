AutomataActionExtractor
=======================

``AutomataActionExtractor`` is a class responsible for extracting
actions from a given input text. Actions are categorized as ToolAction,
AgentAction, and ResultAction, each having their specific behavior and
purpose. This class provides methods to process the input text and
identify each category of actions.

Overview
--------

``AutomataActionExtractor`` primarily consists of a ``classmethod``
called ``extract_actions``, which takes an input text and returns a list
of extracted actions. The extracted actions are represented in their
respective classes - ``ToolAction``, ``AgentAction``, and
``ResultAction``.

Related Symbols
---------------

-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.core.agent.automata_coordinator_agent.AutomataCoordinatorAgent``
-  ``automata.core.tasks.task.AutomataTask``

Example
-------

The following example demonstrates how to extract actions from a given
input text using the ``AutomataActionExtractor`` class:

.. code:: python

   from automata.core.agent.automata_action_extractor import AutomataActionExtractor

   input_text = """
   - thoughts
       - I will use the automata-indexer-retrieve-code tool to retrieve the code for the "run" function from the Automata agent.
   - actions
       - tool_query_0
           - tool_name
               - automata-indexer-retrieve-code
           - tool_args
               - Retrieve the raw code for the function 'run' from the Automata agent, including all necessary imports and docstrings.
   """

   extracted_actions = AutomataActionExtractor.extract_actions(input_text)
   print(extracted_actions[0])

Limitations
-----------

The primary limitation of ``AutomataActionExtractor`` is that it relies
on strict input formatting following the specified structure of thoughts
and actions in the input context. If the input text does not follow the
required format, the extractor might not be able to identify actions
correctly or at all.

Follow-up Questions:
--------------------

-  How can we improve the action extraction process while being flexible
   in input text formatting?
