========================
Team and repository tags
========================

.. image:: http://governance.openstack.org/badges/deb-python-manilaclient.svg
    :target: http://governance.openstack.org/reference/tags/index.html

.. Change things from this point on

Python bindings to the OpenStack Manila API
===========================================

.. image:: https://img.shields.io/pypi/v/python-manilaclient.svg
    :target: https://pypi.python.org/pypi/python-manilaclient/
    :alt: Latest Version

.. image:: https://img.shields.io/pypi/dm/python-manilaclient.svg
    :target: https://pypi.python.org/pypi/python-manilaclient/
    :alt: Downloads

This is a client for the OpenStack Manila API. There's a Python API (the
``manilaclient`` module), and a command-line script (``manila``). Each
implements 100% of the OpenStack Manila API.

See the `OpenStack CLI guide`_ for information on how to use the ``manila``
command-line tool. You may also want to look at the
`OpenStack API documentation`_.

.. _OpenStack CLI Guide: http://docs.openstack.org/user-guide/cli.html
.. _OpenStack API documentation: http://docs.openstack.org/api/

The project is hosted on `Launchpad`_, where bugs can be filed. The code is
hosted on `Github`_. Patches must be submitted using `Gerrit`_, *not* Github
pull requests.

.. _Github: https://github.com/openstack/python-manilaclient
.. _Launchpad: https://launchpad.net/python-manilaclient
.. _Gerrit: http://docs.openstack.org/infra/manual/developers.html#development-workflow

This code is a fork of `Cinderclient`_ of Grizzly release and then it was
developed separately. Cinderclient code is a fork of
`Jacobian's python-cloudservers`__ If you need API support for the Rackspace
API solely or the BSD license, you should use that repository.
python-manilaclient is licensed under the Apache License like the rest of
OpenStack.

.. _Cinderclient: https://github.com/openstack/python-cinderclient
__ http://github.com/jacobian/python-cloudservers

.. contents:: Contents:
   :local:

Command-line API
----------------

Installing this package gets you a shell command, ``manila``, that you
can use to interact with any Rackspace compatible API (including OpenStack).

You'll need to provide your OpenStack username and password. You can do this
with the ``--os-username``, ``--os-password`` and  ``--os-tenant-name``
params, but it's easier to just set them as environment variables::

    export OS_USERNAME=foouser
    export OS_PASSWORD=barpass
    export OS_TENANT_NAME=fooproject

You will also need to define the authentication url either with param
``--os-auth-url`` or as an environment variable::

    export OS_AUTH_URL=http://example.com:5000/v2.0/

Since Keystone can return multiple regions in the Service Catalog, you
can specify the one you want with ``--os-region-name`` (or
``export OS_REGION_NAME``). It defaults to the first in the list returned.

You'll find complete documentation on the shell by running
``manila help``, see ``manila help COMMAND`` for help on a specific command.

Python API
----------

There's also a complete Python API, but it has not yet been documented.

Quick-start using keystone::

    # use v2.0 auth with http://example.com:5000/v2.0/
    >>> from manilaclient.v1 import client
    >>> nt = client.Client(USER, PASS, TENANT, AUTH_URL, service_type="share")
    >>> nt.shares.list()
    [...]

* License: Apache License, Version 2.0
* `PyPi`_ - package installation
* `Online Documentation`_
* `Launchpad project`_ - release management
* `Blueprints`_ - feature specifications
* `Bugs`_ - issue tracking
* `Source`_
* `How to Contribute`_

.. _PyPi: https://pypi.python.org/pypi/python-manilaclient
.. _Online Documentation: http://docs.openstack.org/developer/python-manilaclient
.. _Launchpad project: https://launchpad.net/python-manilaclient
.. _Blueprints: https://blueprints.launchpad.net/python-manilaclient
.. _Bugs: https://bugs.launchpad.net/python-manilaclient
.. _Source: https://git.openstack.org/cgit/openstack/python-manilaclient
.. _How to Contribute: http://docs.openstack.org/infra/manual/developers.html
