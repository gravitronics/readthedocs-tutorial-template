AutomataTaskDatabase
====================

``AutomataTaskDatabase`` is a class responsible for managing the
storage, retrieval, and updating of ``AutomataTask`` objects in a SQLite
database. It provides methods to create the ``tasks`` table if it
doesn’t exist and manipulate task data within the database.

Overview
--------

The ``AutomataTaskDatabase`` is initialized with a path to a SQLite
database. It offers methods to create the ``tasks`` table, retrieve task
information, insert new tasks, and update existing tasks in the
database. The class ensures that any changes to tasks are properly saved
and can be easily retrieved later.

Related Symbols
---------------

-  ``automata.core.tasks.automata_task_registry.AutomataTaskRegistry``
-  ``automata.core.tasks.task.AutomataTask``
-  ``sqlite3``

Example
-------

The following example demonstrates how to create an instance of
``AutomataTaskDatabase``, insert a task, and retrieve it from the
database.

.. code:: python

   from automata.core.tasks.automata_task_registry import AutomataTaskDatabase
   from automata.core.tasks.task import AutomataTask
   from automata.configs.config_enums import AgentConfigName

   # Initialize the database
   db_path = "automata_task_database.sqlite"
   task_db = AutomataTaskDatabase(db_path)

   # Create a sample task
   instructions = "This is a test."
   task = AutomataTask(
       MockRepositoryManager(),
       main_config_name=AgentConfigName.TEST.value,
       generate_deterministic_id=False,
       instructions=instructions,
   )

   # Insert the task into the database
   task_db.insert_task(task)

   # Get the task by its ID
   task_id = task.task_id
   query = f"SELECT json FROM tasks WHERE id = ?"
   params = (task_id,)
   tasks = task_db.get_tasks_by(query, params)

   # Print the retrieved task's instructions
   retrieved_task = tasks[0]
   print(retrieved_task.kwargs["instructions"])  # Output: This is a test.

Please note that ``MockRepositoryManager()`` should be replaced with an
actual instance of the ``RepositoryManager`` or the specific class
implementing a repository manager.

Limitations
-----------

The primary limitation of ``AutomataTaskDatabase`` is its reliance on
SQLite as the storage solution. This might not be suitable for
large-scale applications or scenarios where a more robust, scalable
database solution is required.

Follow-up Questions:
--------------------

-  Does the ``AutomataTaskDatabase`` support concurrent access?

-  What other database solutions could be explored for improving the
   scalability of ``AutomataTaskDatabase``?
