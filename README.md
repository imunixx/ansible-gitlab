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

## Quick Start

- Provide your own inventory file and replace the [inventory](./inventory) file
- Adjust [ansible.cfg](./ansible.cfg) according to your respective credential and user configuration
- Copy the [defaults/main.yml](/roles/gitlab/defaults/main.yml) file from the [gitlab](roles/gitlab) role and adjust it
- Execute the GitLab Role / site.yml Playbook
- Get a GitLab Access Token for API Configuration and set the respective role variable (can only be obtained through GUI)
- Get the Runner Registration Token (https://docs.gitlab.com/runner/register/) and set the respective role variable (can only be obtained from GUI)
- Execute the GitLab role / site.yml playbook again
- GitLab and a Runner should now be up and running
- Checkout https://github.com/KornKalle/gitlab-docker-example and push it to your GitLab Instance for a minimal project which builds a Docker image using GitLab CI

**Please note** Pushing Images from GitLab CI to the GitLab Container Registry does not work over plain http connections and needs SSL to be configured.