# Setting up GitLab + GitLab Runner through Ansible

This repository contains a full ansible setup which is capable of setting up and configuring GitLab + GitLab runner on a single server and 1 to many runner nodes.

## Prerequisites

Roles which are not dedicated for this job are loaded as submodules and should be initialized with 
> git submodule init

## Getting Started

You should provide your own inventory and replace the [inventory](./inventory) file. Also change the credentials according to your needs.
Also refer to the [ansible.cfg](./ansible.cfg) file for credential and user configuration.
You also should copy the [defaults/main.yml](/roles/gitlab/defaults/main.yml) file from the [gitlab](roles/gitlab) role and adjust it.  
For getting an overview have a look at the [group_vars/gitlab.yml](group_vars/gitlab.yml) file.

## Usage
You only need to execute the site.yml playbook or clone the [roles/gitlab](roles/gitlab) directory and integrate into your own Ansible Repository.