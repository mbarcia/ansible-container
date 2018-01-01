
optional arguments
==================

Use the following optional arguments with the ``ansible-container`` command: 

.. option:: -h, --help

Show help message and exit.

.. option:: --debug

Enable debug-level logging for all actions (inside and outside conductor).

.. option:: --devel

Enable "developer mode." This is mostly useful for working on the ansible-container codebase to speed up testing changes. If you aren't testing changes to the ansible-container codebase, it's unlikely you need this option.

Instead of building ansible-container Python source into the conductor container, this option mounts the ansible-container from the host machine for every command. Mounting the source every time means you don't have to rebuild the conductor container to update the code, speeding up the dev-test-run cycle immensely.

.. option:: --engine ENGINE_NAME

Select your container engine and orchestrator. Valid options are: docker, k8s, openshift. Defaults to *docker*.

.. option:: --no-selinux

Stops the 'Z' option from being added to any volumes that get automatically mounted to the build container. For example, the base path to the project is automatically mounted as */ansible-container:Z*.

.. option:: --project BASE_PATH, -p BASE_PATH

Specify a path to your project. Defaults to the current working directory.

.. option:: --vars-files VARS_FILES, --var-file VARS_FILES, --vars-file VARS_FILES

Specify one or more files containing variable definitions to use when performing Jinja2 template rendering while parsing ``container.yml``. Each file should be a an absolute
file path, or a path relative to the *project BASE_PATH* or relative to *project BASE_PATH/ansible*. If the file extension is one of 'yml' or 'yaml', it will be parsed as YAML. Otherwise, it will be parsed as JSON.
