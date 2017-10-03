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
