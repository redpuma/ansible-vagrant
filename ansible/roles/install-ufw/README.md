Install UFW on Ubuntu
=========

This role updates the apt package index files, upgrades host.
Installs UFW package if not already included.
Enables UFW
Restarts host if either upgrade or install happened.
Displays the host's uptime.

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: install-ufw, become: yes }

License
-------

BSD

Author Information
------------------

Stephen James
