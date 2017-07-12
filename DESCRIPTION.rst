REPOS
=====

Role to add yum repos to the systems. It also can configure the epel repository on the system.

You can configure var yum_common_repos on a common var file and yum_repos for each layer var file

Requirements
------------

N/A

Dependencies
------------

N/A

Example Playbook
----------------

.. code::

  - hosts: servers
    roles:
      - { role: repos }
