AutomataConversationDatabase
============================

``AutomataConversationDatabase`` is a database class that helps
managing, storing, and retrieving interactions of an ``AutomataAgent``.
It uses SQLite3 to create a local database and store multiple sessions,
where each session represents a conversation between the user and the
agent.

Overview
--------

The ``AutomataConversationDatabase`` class is responsible for creating a
database connection, initializing the database schema, and providing
utility methods to insert messages and fetch conversations. By using
SQLite3, it supports local storage of the conversations. The class is
closely related to ``AutomataAgent``, mainly focusing on handling the
conversation-oriented data.

Related Symbols
---------------

-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.config.CONVERSATION_DB_PATH``
-  ``automata.core.base.openai.OpenAIChatMessage``

Example
-------

The following example demonstrates how to create and utilize an
``AutomataConversationDatabase`` instance to store and retrieve
messages.

.. code:: python

   from automata.core.agent.automata_database_manager import AutomataConversationDatabase

   session_id = "example-session"
   database = AutomataConversationDatabase(session_id)

   # Insert messages
   database.put_message("user", "Hello, Assistant.", 0)
   database.put_message("assistant", "Hello, User!", 1)

   # Get conversations
   conversations = database.get_conversations()
   for message in conversations:
       print(f"{message.role}: {message.content}")

   # Close the connection
   del database

Limitations
-----------

The primary limitation of ``AutomataConversationDatabase`` is its use of
SQLite3, which is a local file-based database. This restricts the
availability of the data to the machine where it is stored and may lead
to concurrency issues when multiple instances try to access the same
data.

Follow-up Questions:
--------------------

-  Can the ``AutomataConversationDatabase`` be extended or adapted to
   support other database systems, such as PostgreSQL or MySQL?
