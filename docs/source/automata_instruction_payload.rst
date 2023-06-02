AutomataInstructionPayload
==========================

``AutomataInstructionPayload`` is a dataclass that holds the payload
data used for formatting the introduction instruction. It is typically
passed as an attribute for ``AutomataAgentConfig``. The class has fields
for the agents’ message, overview, and tools, and provides a method for
validating the given fields.

Overview
--------

The main responsibility of ``AutomataInstructionPayload`` is to store
data required for formatting introduction instructions for an agent. It
is usually passed as part of the ``AutomataAgentConfig``, which then
incorporates it into the instruction template. The class makes sure that
the necessary fields are provided and initialized correctly.

Related Symbols
---------------

-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.config_enums.InstructionConfigVersion``

Example
-------

The following example demonstrates how to create an instance of
``AutomataInstructionPayload`` with custom data:

.. code:: python

   from automata.configs.automata_agent_configs import AutomataInstructionPayload

   agents_message = "This agent helps in resolving programming-related queries."
   overview = "It supports Python, JavaScript, and Java with a variety of tools."
   tools = "Available tools include: code formatter, debugger, and syntax analyzer."

   instruction_payload = AutomataInstructionPayload(
       agents_message=agents_message,
       overview=overview,
       tools=tools
   )

Limitations
-----------

The main limitation of ``AutomataInstructionPayload`` is that it only
supports a fixed set of fields (agents_message, overview, and tools). If
there is a need to include more fields or data in the introduction
instruction, users would need to modify the class itself to accommodate
the additional fields.

Follow-up Questions:
--------------------

-  How can we make ``AutomataInstructionPayload`` more flexible to
   accommodate custom fields more easily?
