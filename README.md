Ansible Role - Nginx
====================

A nginx role to install ruby on elao symfony standard vagrant box


Requirements
------------

This role only run on elao symfony standard vagrant box. See https://vagrantcloud.com/elao/symfony-standard-debian

Role Handlers
-------------

    nginx restart  # Restart nginx service


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: elao.nginx }


License
-------

MIT


Author Information
------------------

http://www.elao.com/
