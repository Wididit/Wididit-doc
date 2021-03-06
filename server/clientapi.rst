.. _server-clientapi:

**********
Client API
**********

Design
======

Formats
-------

All requests to the Wididit API must use the HTTP protocol, and several output
formats are available:

* json: JavaScript Object Notation, which is the recommended format
* xml: eXtensible Markup Language
* yaml: YAML Ain't Markup Language

Some others might be available depending on the Django-Piston version.

The URL prefix is `/api/<format>/` (where `format` is the output format
you want). In the next sections, we will ommit this prefix.

Status codes
------------

See `this table`_.

.. _this table: https://bitbucket.org/jespern/django-piston/wiki/Documentation#!helpers-utils-decorators

Authentication
--------------

For the moment, the only available authentication uses the HTTP_AUTHORIZATION
header (a base64 representation of `<login>:<password>`), but we are planning
to use OAuth.

Servers
=======

Fields
------

self

        `True` if this is the server you are querying, `False` otherwise.

hostname

        The hostname of the server.

List
----

To get a list of all servers in the server's :ref:`concepts-network`, perform
a GET request to `/server/`.


People
======

Fields
------

username

        The username of this people.

server

        The server on which this people is registered.

biography

        An autobiography written by the user owning this account.

List
----

Perform a get request to `/people/`

Get a profile
-------------

Perform a request to `/people/<username>/` where `<username>` is a :ref:`userid`.


Entries
=======

Fields
------

shared_by

        A list of user which shared this entry.

.. NOTE::

        This fields are inspired from the Atom specification.

id

        The ID of this entry. It is unique against the user (and not against
        the server or the network).

content

        The content of this entry.

author

        The people who wrote this entry.

category

        A tag.

contributors

        The list of users which have write access to the entry. Does not
        contain the author.

generator

        The name of the client used to post this entry.

published

        The publication date.

rights

        The license of the entry.

source

        Unused.

subtitle

        A subtitle for the entry.

summary

        A summary.

title

        The title of the entry.

updated

        Last update date.

.. NOTE::

        This field is inspired from the Atom Threading Extensions specification.

in_reply_to

        If this entry is a reply, this field is the original entry.



List all entries
----------------

Perform a GET request to `/entry/`

You can supply filters to the search, as GET parameters:

tag=<data>

        All entries must be tagged with this tag.

        If you supply this parameter twice (or more), it will act as a `AND`
        clause.

content=<data>

        All entries must contain the exact string.

        If you supply this parameter twice (or more), it will act as a `AND`
        clause.

author=<data>

        The entry must have been created by the given :ref:`userid`.

        If you supply this parameter twice (or more), it will act as a `OR`
        clause (because a single entry cannot have multiple authors).

in_reply_to=<data>

        Must be in the format `<userid>/<entryid>`.

        All entries must be a reply to the specified entry.

        You cannot supply this parameter twice.

share

        Includes shared entries.

nonative

        Strips entries that have not been shared.

Get an entry
------------

Perform a GET request to `/entry/<userid>/<id>/`.

Create an entry
---------------

.. NOTE::

        You must be authenticated.

Perform a POST request to `/entry/`. All fields but `generator`,
`title`, and `content` are optional.

`contributors` must be a list of user ids, separated by spaces.

You cannot edit `id`, `author`, `published` and `updated`.

Update an entry
---------------

Same as entry creation, but with a PUT request to `/entry/<userid>/<entryid>/`.

Delete an entry
---------------

.. NOTE::

        You must be authenticated and have write access to the entry.

Perform a DELETE request to `/entry/<userid>/<entryid>/`.
