ansible-pxe
=============

This is a WIP :)

.. image:: http://img.shields.io/badge/ansible--galaxy-pxe-blue.svg
  :target: https://galaxy.ansible.com/narfman0/pxe/

.. image:: https://travis-ci.org/narfman0/ansible-pxe.png?branch=master
    :target: https://travis-ci.org/narfman0/ansible-pxe

Ansible module for pxe project.

Usage
-----


A vagrant file has been included for easier testing. To use::

    vagrant up --provider virtualbox

This will provision the machine such that a working pxe
is ready to run. Some tweaks to sound devices may be needed.

Raspberry pis need a few special tweaks, and some special
logic is reservered for them. To identify your device(s) as
raspberry pis, please but them in the `rasppi` group in e.g.
`/etc/ansible/hosts`.

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
      - { role: narfman0.pxe }

TODO
----

* WIP - logic and trivial passing unit test(s)

License
-------

Please see included LICENSE file for license specifics

Copyright 2017 Jon Robison
