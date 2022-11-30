# Setting up GitLab + GitLab Runner through Ansible

This repository contains a full ansible setup which is capable of setting up and configuring GitLab + GitLab runner on a single server and 1 to many runner nodes.

## Prerequisites

Roles which are not dedicated for this job are loaded as submodules and should be initialized with 
> git submodule init

'sudo' won't be installed on a plain Debian Netinstall, install it via:
> apt update && apt install sudo

## Getting Started

For a detailed documentation of the GitLab role, see [roles/gitlab/README.md](roles/gitlab/README.md).  
For a detailed documentation of the GitLab Runner role, see [roles/gitlab_runner/README.md](roles/gitlab_runner/README.md)

You should provide your own inventory and replace the [inventory](./inventory) file. Also change the credentials according to your needs.
Also refer to the [ansible.cfg](./ansible.cfg) file for credential and user configuration.
You also should copy the [defaults/main.yml](/roles/gitlab/defaults/main.yml) file from the [gitlab](roles/gitlab) role and adjust it.  
For getting an overview have a look at the [group_vars/gitlab.yml](group_vars/gitlab.yml) file.

## Quick Start

These instructions will set up a functioning GitLab Instance + 1 Runner asap.
If you want to adjust settings, credentials and other parameters, pleases follow the documentation of the GitLab and GitLab Runner role.

- Create 2 virtual Debian machines
- Setup sudo and deploy your ssh key
- Provide your own inventory file and replace the [inventory](./inventory) file with your hosts
- Adjust [ansible.cfg](./ansible.cfg) according to your respective credential and user configuration
  - Especially the user and become parameters
- Create a vaultpassword file on the root level of the repository and fill it with your own secure vaultpassword
- Copy the [defaults/main.yml](/roles/gitlab/defaults/main.yml) file from the [gitlab](roles/gitlab) role and adjust it
  - Remember to always vault your credentials (https://docs.ansible.com/ansible/latest/vault_guide/index.html)
- Execute the GitLab Role / site.yml Playbook
  - GitLab should now be running and you can login with your provided initial password
- Get a GitLab Access Token for API Configuration and set the respective role variable (https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html)
- Get the Runner Registration Token (https://docs.gitlab.com/runner/register/) and set the respective role variable
- Execute the GitLab role / site.yml playbook again
- GitLab and a Runner should now be up and running
- Checkout https://github.com/KornKalle/gitlab-docker-example and push it to your GitLab Instance for a minimal project which builds a Docker image using GitLab CI

**Please note** Pushing Images from GitLab CI to the GitLab Container Registry does not work over plain http connections and needs SSL to be configured.