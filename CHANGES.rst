Tequila-dokku
=============

Changes

v 0.3.0 on Dec 4, 2017
----------------------

* ``include`` directive is now [deprecated](https://github.com/ansible/ansible/blob/v2.4.0.0-1/CHANGELOG.md#major-changes), switch to use ``include_tasks``
* Only run install tasks if not upgrading
* Unhold dpkg-selections packages before upgrading


v 0.2.0 on Oct 4, 2017
----------------------

* Open 80/443 ports and add dokku user to login group
* Add tasks to support upgrading dokku


v 0.1.0 on Oct 3, 2017
----------------------

* Initial release
