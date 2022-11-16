GitLab
=========

This role installs, configures and manages a GitLab Omnibus installation on Debian Systems. Core features are seamless installation and basic configuration of core features, which are:

- SMTP
- LDAP Auth
- Backups and their schedule
- Container registry and its cleanup policy
- GitLab Dependency Proxy
- Core Security Requirements for ssh keys


Requirements
------------

Python should be <=3.9 on the target host, the GitLab Hardware Requirements should be met (2 Cores / 4GB RAM)

Role Variables
--------------

You can find an overview over all available variables in [defaults/main.yml](defaults/main.yml), naming matches the GitLab variables as close as possible.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: gitlab
      roles:
         - { role: kornkalle.gitlab }

License
-------

Proprietary

Author Information
------------------

nils@klackwerk.de
