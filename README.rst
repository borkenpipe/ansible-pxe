ansible-erpxe
=============

This is a WIP :)

.. image:: http://img.shields.io/badge/ansible--galaxy-erpxe-blue.svg
  :target: https://galaxy.ansible.com/narfman0/erpxe/

.. image:: https://travis-ci.org/narfman0/ansible-erpxe.png?branch=master
    :target: https://travis-ci.org/narfman0/ansible-erpxe

Ansible module for erpxe project.

Usage
-----


A vagrant file has been included for easier testing. To use::

    vagrant up --provider virtualbox

This will provision the machine such that a working erpxe
is ready to run. Some tweaks to sound devices may be needed.

Raspberry pis need a few special tweaks, and some special
logic is reservered for them. To identify your device(s) as
raspberry pis, please but them in the `rasppi` group in e.g.
`/etc/ansible/hosts`.

Running playbook directly
~~~~~~~~~~~~~~~~~~~~~~~~~

I have a erpxe host defined in `/etc/ansible/hosts`, that I
put in the rasppi group::

    [erpxe]
    erpxe1

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
      - { role: narfman0.erpxe }

TODO
----

* WIP - logic and trivial passing unit test(s)

License
-------

Please see included LICENSE file for license specifics

Copyright 2017 Jon Robison
