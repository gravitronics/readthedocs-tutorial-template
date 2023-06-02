automata.configs.automata_agent_config_utils.AutomataAgentConfigBuilder
=======================================================================

``AutomataAgentConfigBuilder`` is a builder class for constructing
instances of ``AutomataAgentConfig``. It provides a flexible and
easy-to-use interface for setting various properties of the agent
configuration before instantiation.

Overview
--------

The ``AutomataAgentConfigBuilder`` class enables users to create custom
configurations for their agents by setting attributes such as the
evaluation mode, helper agent configurations, instruction payload,
instruction version, low-level manipulation (LLM) toolkits, model,
session ID, stream mode, temperature, and verbose mode. The builder
pattern makes it easy to construct ``AutomataAgentConfig`` instances
with different combinations of these properties and create agents with
customized behaviors.

Related Symbols
---------------

-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.configs.automata_agent_configs.AutomataAgentConfig``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.tool_management.tool_management_utils.build_llm_toolkits``

Example
-------

The following example demonstrates how to use the
``AutomataAgentConfigBuilder`` to create a custom
``AutomataAgentConfig`` instance:

.. code:: python

   from automata.configs.automata_agent_config_utils import AutomataAgentConfigBuilder
   from automata.configs.automata_agent_configs import AutomataInstructionPayload

   custom_instruction_payload = AutomataInstructionPayload(tools=[])

   builder = AutomataAgentConfigBuilder()
   builder.with_model("gpt-4")\
          .with_eval_mode(True)\
          .with_instruction_payload(custom_instruction_payload)\
          .with_max_iters(100)

   custom_agent_config = builder.build()

Limitations
-----------

``AutomataAgentConfigBuilder`` class assumes that the user provides
valid input values for the respective properties being set. If the
provided values are not valid, it might lead to inconsistent agent
behavior or errors during the agent’s execution.

Follow-up Questions:
--------------------

-  Can we add input validation while setting the properties in
   ``AutomataAgentConfigBuilder`` to avoid runtime errors?

Footnotes
---------

-  Examples in this documentation have been updated with actual
   underlying objects instead of ‘Mock’ objects and are ready for
   execution.
