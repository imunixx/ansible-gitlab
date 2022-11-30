GitLab
=========

This role installs, configures and manages a GitLab Omnibus installation on Debian Systems. Core features are seamless installation and basic configuration of core features, which are:

- SMTP
- LDAP Auth
- Backups and their schedule
- Container registry and its cleanup policy
- GitLab Dependency Proxy
- Core Security Requirements for ssh keys

**Please note**  
You will need to run this role twice when performing a first-time installation.  
You will need to get a GitLab API Access Token via GitLab GUI after installation for configurations made through GitLab API.  
See https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html for further information.

Requirements
------------

Python should be <=3.9 on the target host, the GitLab Hardware Requirements should be met (2 Cores / 4GB RAM).  
**You will need to set the gitlab_initial_root_password parameter for a successful first-time setup.**

Role Variables
--------------

You can find an overview over all available variables in [defaults/main.yml](defaults/main.yml), naming matches the GitLab variables as close as possible.

Example Playbook
----------------

    - hosts: gitlab
      roles:
         - { role: kornkalle.gitlab }

License
-------

Proprietary

Author Information
------------------

nils@klackwerk.de
