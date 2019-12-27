
# Overview

Minimal Ansible playbook for installation of Mattermost for AWS Linux 2 that uses AWS Services wherever possible

Assumes

- Will be executed by packer or upon initial bootup with Ansible local to install software
- Is run on boot through cloud-init after infrastructure is deployed via terraform
- Python 3.7 / Ansible 2.9.2

# References & Shoutouts

I looked at https://github.com/tjtoml/mattermost-ansible but used very little code because it is a broader use case (pure standalone and multi-OS)
