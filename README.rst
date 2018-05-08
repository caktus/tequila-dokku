tequila-dokku
=============

This repository holds an `Ansible <http://www.ansible.com/home>`_ role
that is installable using ``ansible-galaxy``.  This role contains
tasks used to install and set up Dokku.

License
-------

This Ansible role is released under the BSD License.  See the `LICENSE
<https://github.com/caktus/tequila-dokku/blob/master/LICENSE>`_ file
for more details.


Contributing
------------

If you think you've found a bug or are interested in contributing to
this project check out `tequila-dokku on Github
<https://github.com/caktus/tequila-dokku>`_.

Development sponsored by `Caktus Consulting Group, LLC
<http://www.caktusgroup.com/services>`_.


Installation
------------

Add a requirement to your ``requirements.yml`` file::

    ---
    # file: deployment/requirements.yml
    - src: https://github.com/caktus/tequila-dokku
      version: 0.1.0

Run ``ansible-galaxy`` with your requirements file ::

    $ ansible-galaxy install -r requirements.yml

or, alternatively, run it directly against the url ::

    $ ansible-galaxy install git+https://github.com/caktus/tequila-dokku

The project then should have access to the ``tequila-dokku`` role in
its playbooks.

Variables
---------

The following variables can be used to control behavior. They are
listed with their original defaults.

Debconf options (see `here <http://dokku.viewdocs.io/dokku/getting-started/install/debian/#debconf-options>`_ for docs)::

    dokku_vhost_enable: "true"
    dokku_web_config: "false"
    dokku_skip_key_file: "true"
    dokku_key_file: ""
    dokku_hostname: 'dokku.me'

Docker and dokku versions, and whether to do
an upgrade (otherwise does an install)::

    docker_version: '17.06.2~ce-0~ubuntu'  # pin version to manage upgrades
    dokku_version: '0.10.4'  # pin version to manage upgrades

Non-core plugins that you would like to be installed::

    dokku_plugins:
    - name: postgres
      src: https://github.com/dokku/dokku-postgres.git
      version: 1.2.7
    - name: letsencrypt
      src: https://github.com/dokku/dokku-letsencrypt.git
      version: 0.8.8

Usage
-----

Set the variables above the way you want them. Then invoke the role from
your playbook.

Example::

      - name: Configure dokku
        hosts: dokku-servers
        become: yes
        roles:
          - tequila-dokku

