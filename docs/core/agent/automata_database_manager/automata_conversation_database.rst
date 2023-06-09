AutomataConversationDatabase
============================

``AutomataConversationDatabase`` is a class that manages the storage and
retrieval of interactions between the agent and the user in a SQLite
database. It includes methods to interact with the database such as
inserting messages and loading conversations. The database stores
interactions with a session ID, role, and content, allowing the agent to
maintain the session state and continue interacting from previous
conversations if needed.

Overview
--------

The primary purpose of ``AutomataConversationDatabase`` is to handle
database operations for an agent’s conversations. It connects to a
SQLite database defined by the ``CONVERSATION_DB_PATH``, and provides
methods for inserting messages and loading conversations. Instance
variables include ``self.session_id``, ``self.conn``, and
``self.cursor``, which store the session ID, database connection, and
database cursor, respectively.

Related Symbols
---------------

-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.tasks.task.AutomataTask``
-  ``automata.core.coordinator.automata_coordinator.AutomataCoordinator``

Methods
-------

-  ``__del__(self)``: Closes the connection to the agent’s database.
-  ``__init__(self, session_id: str)``: Initializes the
   ``AutomataConversationDatabase`` with the given session ID.
-  ``get_conversations(self) -> List[OpenAIChatMessage]``: Loads
   previous interactions from the database and populates the messages
   list.
-  ``put_message(self, role: str, content: str, interaction_id: int)``:
   Inserts the message into the appropriate session and interaction ID.

Example
-------

The following example demonstrates how to create an instance of
``AutomataConversationDatabase``, store, and retrieve messages.

.. code:: python

   from automata.core.agent.automata_database_manager import AutomataConversationDatabase
   from automata.core.messages import OpenAIChatMessage

   session_id = "123456"
   db_manager = AutomataConversationDatabase(session_id=session_id)

   # Insert a message
   saved_message = db_manager.put_message("user", "Hello, Assistant!", 0)

   # Retrieve the messages
   loaded_messages = db_manager.get_conversations()

   # Check if the messages are correctly saved and retrieved
   assert len(loaded_messages) == 1
   assert loaded_messages[0].role == "user"
   assert loaded_messages[0].content == "Hello, Assistant!"

Limitations
-----------

``AutomataConversationDatabase`` is specifically designed for SQLite
databases and would require modification to support other types of
databases. Additionally, it only provides basic methods for inserting
and retrieving messages. For more complex operations or filtering of
messages, custom methods would need to be implemented.

Follow-up Questions:
--------------------

-  Can the ``AutomataConversationDatabase`` be extended to support
   alternative database types like PostgreSQL or MongoDB?
-  What other functionalities can be added to
   ``AutomataConversationDatabase`` to enable more nuanced handling of
   messages?
