================
Storage Adapters
================

Storage adapters provide an interface that allows ChatterBot
to connect to different storage technologies.

The storage adapter that your bot uses can be specified by setting
the ``storage_adapter`` parameter to the import path of the
storage adapter you want to use. 

.. code-block:: python

   chatbot = ChatBot(
       "My ChatterBot",
       storage_adapter="chatterbot.storage.SQLStorageAdapter"
   )

Built-in Storage Adapters
=========================

.. toctree::
   :maxdepth: 2

   redis
   mongodb
   sql
   ../django/index

Common storage adapter attributes
=================================

Each storage adapter inherits the following attributes and methods.

.. autoclass:: chatterbot.storage.StorageAdapter
   :members:

Database Migrations
===================

Various frameworks such as Django and SQL Alchemy support
functionality that allows revisions to be made to databases
programmatically. This makes it possible for updates and
revisions to structures in the database to be be applied
in consecutive version releases.

The following explains the included migration process for
each of the databases that ChatterBot comes with support for.

* Django: Full schema migrations and data migrations will
  be included with each release.
* SQL Alchemy: No migrations are currently provided in
  releases. If you require migrations between versions
  `Alembic`_ is the recommended solution for generating them.
* MongoDB: No migrations are provided.
* Redis: No migrations are provided.

Further Reading
===============

.. toctree::
   :maxdepth: 2

   text-search
   create-a-storage-adapter

.. _Alembic: https://alembic.sqlalchemy.org
