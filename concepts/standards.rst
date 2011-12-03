.. _concepts-standards:

*********
Standards
*********

Wididit is based only on open standards.

Wididit
=======

The Wididit server itself uses parts of the :ref:`python`. For example
the constants module is used to create data models.

HTTP, Atom, XML
===============

The API uses a REST model, based on HTTP (AtomPub, actually).

Atom is a core feature of Wididit; data models are based on the Atom protocol.
All features available through the web view are available through the API, in
Atom format if possible (for example to share network links, Atom is not
the right format).
