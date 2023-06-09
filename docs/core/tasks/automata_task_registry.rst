AutomataTaskRegistry
====================

``AutomataTaskRegistry`` is a class used to manage and interact with
tasks in an Automata system. It helps store, load, update, and commit
tasks to a remote repository.

Overview
--------

``AutomataTaskRegistry`` provides an interface to interact with tasks
while working with the Automata system. It takes in a
``AutomataTaskDatabase`` object as a data store and a ``GitHubManager``
object for interaction with a remote repository. It provides various
methods like ``commit_task``, ``get_all_task_summaries``,
``get_all_tasks``, ``get_task_by_id``, ``initialize_task``, and
``update_task`` to manage tasks and their states.

Related Symbols
---------------

-  ``automata.core.tasks.task.AutomataTask``
-  ``automata.configs.config_enums.AgentConfigName``
-  ``automata.core.agent.automata_agent.AutomataAgent``
-  ``automata.core.tasks.automata_task_executor.TaskExecutor``

Examples
--------

The following example demonstrates how to create an instance of
``AutomataTaskRegistry``

.. code:: python

   from automata.core.tasks.automata_task_registry import AutomataTaskRegistry
   from automata.core.tasks.automata_task_database import AutomataTaskDatabase
   from automata.core.github.github_manager import GitHubManager

   db = AutomataTaskDatabase()
   github_manager = GitHubManager("<YOUR_GITHUB_ACCESS_TOKEN>")

   registry = AutomataTaskRegistry(db, github_manager)

To get a task by its ID from the registry:

.. code:: python

   task_id = "<TASK_ID>"
   task = registry.get_task_by_id(task_id)

Limitations
-----------

The primary limitation of ``AutomataTaskRegistry`` is that it assumes
the use of a specific data store (``AutomataTaskDatabase``) and a
particular Git hosting service (GitHub), making it less flexible for
other data store and repository hosting services.

Follow-up Questions:
--------------------

-  Can we make ``AutomataTaskRegistry`` more generic to support
   different datastores and repository hosting services?
