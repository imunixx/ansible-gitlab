GitLab Runner
=========

This role installs GitLab Runner using the docker executor on Debian Systems.
The installations uses Docker socket binding as default and is compatible to docker-in-docker builds.

Requirements
------------

Docker must be installed on the target system

Role Variables
--------------

You can find an overview over all available variables in [defaults/main.yml](defaults/main.yml), naming matches the GitLab variables as close as possible.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: gitlab_runner
      roles:
         - { role: kornkalle.docker }
         - { role: kornkalle.gitlab_runner }

License
-------

Proprietary

Author Information
------------------

nils@klackwerk.de
