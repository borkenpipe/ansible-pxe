ansible-pxe
=============

.. image:: http://img.shields.io/badge/ansible--galaxy-pxe-blue.svg
  :target: https://galaxy.ansible.com/narfman0/pxe/

.. image:: https://travis-ci.org/narfman0/ansible-pxe.png?branch=master
    :target: https://travis-ci.org/narfman0/ansible-pxe

Ansible module for pxe

Usage
-----


A vagrant file has been included for easier testing. To use::

    vagrant up --provider virtualbox

This will provision the machine such that a working pxe
is ready to run.

This is not a strict dependency, but something like narfman0.tftp
would be wise to configure as a complementary target. `pxe_root_path`
would then be updated to the target directory for your tftp root path.

Running playbook directly
~~~~~~~~~~~~~~~~~~~~~~~~~

I have a pxe host defined in `/etc/ansible/hosts`, that I
put in the rasppi group::

    [pxe]
    pxe1

Assuming you have hosts identified (overriding playbook vars
or globally in `/etc/ansible/hosts`), you may invoke the
playbook directly with::

    ansible-playbook playbook.yml -v

Example
-------

Playbook::

    - hosts: servers
      vars_files:
        - vars/main.yml
      roles:
      - { role: narfman0.tftp }
      - { role: narfman0.pxe }

License
-------

Please see included LICENSE file for license specifics

Copyright 2017 Jon Robison
