AutomataActionExtractor
=======================

``AutomataActionExtractor`` is a class responsible for extracting a list
of actions from a given input text. The extracted actions can be from
any of the supported ActionTypes, such as AgentAction, ToolAction, or
ResultAction. These ActionTypes define the actions that an
``AutomataAgent`` can take, and the extraction process extracts them
from the given text in a structured format.

Overview
--------

The main method of the ``AutomataActionExtractor`` class is
``extract_actions``, which accepts a text input and returns a list of
ActionTypes objects. These ActionTypes objects can then be processed by
the agent for execution. The class provides a simple and convenient way
for the agent to analyze text input and extract useful information for
further action.

Related Symbols
---------------

-  ``automata.core.agent.automata_actions.ActionTypes``
-  ``automata.core.agent.automata_actions.AgentAction``
-  ``automata.core.agent.automata_actions.ToolAction``
-  ``automata.core.agent.automata_actions.ResultAction``
-  ``automata.core.agent.automata_agent_enums.ActionIndicator``
-  ``automata.core.agent.automata_agent_enums.AgentField``
-  ``automata.core.agent.automata_agent_enums.ResultField``
-  ``automata.core.agent.automata_agent_enums.ToolField``
-  ``automata.core.agent.automata_agent.AutomataAgent``

Example
-------

The following is an example demonstrating how to use the
``AutomataActionExtractor`` class to extract actions from a given input
text.

.. code:: python

   from automata.core.agent.automata_action_extractor import AutomataActionExtractor

   input_text = """- thoughts
       - I will use the automata-indexer tool to retrieve the code for the function "run".
   - actions
       - tool_query_0
           - tool_name
               - automata-indexer
           - tool_args
               - Retrieve the code for the function 'run'."""

   actions = AutomataActionExtractor.extract_actions(input_text)

Limitations
-----------

The primary limitation of the ``AutomataActionExtractor`` is that it
assumes a specific input text structure for the action extraction. This
structure is based on YAML-like syntax, which may not be the most
intuitive or familiar format for users. The class may not handle
unsupported or edge-case input structures as expected, leading to
incorrect action extraction.

Follow-up Questions:
--------------------

-  How can the text input syntax be made more robust and resilient to
   different input styles or formats?
