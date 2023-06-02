AutomataTaskRegistry
====================

``AutomataTaskRegistry`` is a versatile registry class that manages and
tracks ``AutomataTask`` instances. It provides utility methods for
committing task to a remote repository, querying tasks based on their
status, and updating tasks in the registry.

Overview
--------

``AutomataTaskRegistry`` is initialized by providing an
``AutomataTaskDatabase`` instance and a ``GitHubManager`` instance. The
class provides various methods to interact with and manage tasks within
the registry. Key methods include ``commit_task``,
``get_all_task_summaries``, ``get_all_tasks``, ``get_task_by_id``,
``initialize_task``, and ``update_task.``

Related Symbols
---------------

-  ``automata.core.tasks.task.AutomataTask``
-  ``automata.core.tasks.automata_task_executor.TaskExecutor``
-  ``automata.core.base.github_manager.GitHubManager``

Example
-------

The following is an example demonstrating how to create an instance of
``AutomataTaskRegistry`` and interact with tasks.

.. code:: python

   from automata.core.tasks.automata_task_registry import AutomataTaskRegistry
   from automata.core.tasks.task import AutomataTask
   from automata.core.base.github_manager import GitHubManager
   from automata.core.database.automata_task_database import AutomataTaskDatabase

   # Initialize instances required for AutomataTaskRegistry
   db = AutomataTaskDatabase()
   github_manager = GitHubManager()

   # Create AutomataTaskRegistry instance
   task_registry = AutomataTaskRegistry(db=db, github_manager=github_manager)

   # Create and initialize a new task
   task = AutomataTask(*args, **kwargs)
   task_registry.initialize_task(task)

   # Get task summaries
   task_summaries = task_registry.get_all_task_summaries()

   # Get task by id
   task_id = "example_task_id"
   task_by_id = task_registry.get_task_by_id(task_id)

   # Update a task's status in the registry
   task.status = TaskStatus.SUCCESS
   task_registry.update_task(task)

   # Commit a task to a remote repository
   commit_message = "Task execution completed successfully"
   pull_title = "Add task result to the main branch"
   pull_body = "This pull request includes the result of the executed task."
   pull_branch_name = "feature/task_result"

   pull_request_url = task_registry.commit_task(task, github_manager, commit_message,
                                                pull_title, pull_body, pull_branch_name)

Limitations
-----------

The primary limitation of the ``AutomataTaskRegistry`` is that it relies
on the provided ``AutomataTaskDatabase`` and ``GitHubManager`` instances
for managing tasks and interacting with the remote repository. Any
issues with these dependencies could impact the functionality of the
registry class.

Follow-up Questions:
--------------------

-  How can we handle errors and exceptions while interacting with
   ``AutomataTaskDatabase`` and ``GitHubManager`` within
   ``AutomataTaskRegistry``?

-  Can custom databases and repository managers be supported by
   ``AutomataTaskRegistry``?
