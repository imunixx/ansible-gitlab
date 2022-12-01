GitLab Runner
=========

This role installs GitLab Runner using the docker executor on Debian Systems.
The installations uses Docker socket binding as default and is compatible to docker-in-docker builds.

Requirements
------------

Docker must be installed on the target system.  
**You need to obtain the GitLab Runner registration token from your GitLab Instance (https://docs.gitlab.com/runner/register/)**

Role Variables
--------------

You can find an overview over all available variables in [defaults/main.yml](defaults/main.yml), naming matches the GitLab variables as close as possible.

Example Playbook
----------------

    - hosts: gitlab_runner
      roles:
         - { role: kornkalle.docker }
         - { role: kornkalle.gitlab_runner }

License
-------

MIT

Author Information
------------------

nils@klackwerk.de
