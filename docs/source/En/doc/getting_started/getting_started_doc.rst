Getting started
----

First, create project.

In LoadDensity, you can create a project which will automatically generate sample files once the project is created.
These sample files include a Python executor file and a keyword.json file.

To create a project, you can use the following method:

.. code-block:: python

    from je_load_density import create_project_dir
    # create on current workdir
    create_project_dir()
    # create project on project_path
    create_project_dir("project_path")
    # create project on project_path and dir name is My First Project
    create_project_dir("project_path", "My First Project")

Or using CLI, this will generate a project at the project_path location.

.. code-block:: console

    python -m je_load_density --create_project project_path

Then, you can enter the project folder,
navigate to the executor folder,
choose one of the executors to run and observe.
The keyword.json file in the keyword folder defines the actions to be executed.

If you want to execute using pure Python, you can refer to the following example:

.. code-block:: python

    from je_load_density import start_test

    start_test(
        {
            "user": "fast_http_user",
        },
        50, 10, 5,
        **{
            "tasks": {
                "get": {"request_url": "http://httpbin.org/get"},
                "post": {"request_url": "http://httpbin.org/post"}
            }
        }
    )