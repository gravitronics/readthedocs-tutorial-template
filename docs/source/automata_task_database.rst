AutomataTaskDatabase
====================

``AutomataTaskDatabase`` is a class used to store and manage tasks in an
SQLite database. It provides methods to create a database table,
retrieve task summaries, get tasks, insert tasks, and update tasks. This
class is used in conjunction with the ``AutomataTaskRegistry`` and
``AutomataTask`` classes.

Overview
--------

``AutomataTaskDatabase`` provides a convenient way to store and manage
tasks in an SQLite database. It is initialized with a database path and
uses methods to interact with the database to create, retrieve, and
update tasks. It is designed to work with the ``AutomataTask`` class and
offers methods to get task summaries and tasks based on SQLite queries.

Related Symbols
---------------

-  ``automata.core.tasks.task.AutomataTask``
-  ``automata.core.tasks.automata_task_registry.AutomataTaskRegistry``
-  ``sqlite3``

Example
-------

The following example demonstrates how to create an instance of
``AutomataTaskDatabase`` and store ``AutomataTask`` objects in the
SQLite database.

.. code:: python

   from sqlite3 import connect
   from automata.core.tasks.automata_task_registry import AutomataTaskDatabase
   from automata.core.tasks.task import AutomataTask

   # Initialize the AutomataTaskDatabase instance
   db_path = "path/to/your/database.sqlite3"
   task_database = AutomataTaskDatabase(db_path)

   # Creating an AutomataTask object
   task = AutomataTask(...)

   # Inserting task into the database
   task_database.insert_task(task)

   # Updating the task status
   task.status = TaskStatus.SUCCESS
   task_database.update_task(task)

   # Retrieve tasks from the database using a query
   query = "SELECT * FROM tasks WHERE status = ?"
   params = (TaskStatus.SUCCESS.value,)
   tasks = task_database.get_tasks_by(query, params)

Limitations
-----------

``AutomataTaskDatabase`` relies on the SQLite database to store and
manage tasks. It uses the provided database path to create a connection,
and hence assumes that the database file is available at the specified
path. It may not be suitable for applications requiring a different type
of database or more advanced functionality.

Follow-up Questions:
--------------------

-  How can we adapt the ``AutomataTaskDatabase`` class to work with
   other types of databases?
-  Is there a better alternative to SQLite for storing and managing
   tasks in this context?
