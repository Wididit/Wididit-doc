.. _concepts-entries:

*******
Entries
*******

What we call an entry is actually a message. But the Atom protocol defines
it as an entry, so do we.

Writing an entry
================

When someone writes an entry, (s)he submits it to a server, and then the
server makes it publicly available, both with displaying it on the user
page and with sending it to people who subscribed to the user (even if
they are on other servers).

Deleting an entry
=================

There are two kinds of social networks:

* Centralized ones, which allows to delete your own messages.
* Decentralized ones, which does not allow such a deletion.

Even if Wididit is not centralized, it allows messages deletion. Actually,
the original message is only stored in the server where the author is
register. Other servers just keep a cache, and they don't have any
authority to prove that the author actually wrote this.

We believe content can't be really deleted, even on centralized network
(did you ever heard of clipboard, Google Cache, etc?), so we only remove
proofs that the author actually wrote this.

Of course, when you delete a message, the server deletes it itself.

Sharing an entry
================

Sharing! The reason to be of all great social networks (it includes Twitter,
StatusNet, SeenThis; but excludes Facebook).

When you share an entry, it will appear in your own feed, but you obviously
won't be marked as its author. Wididit also keep tracks of shares: a tree is
created (Z shared from Y, which shared an entry from X).

Wiki
====

Wididit enables you to turn an entry into a wiki. It will allow anybody you
allow (groups supported) to edit this entry. History is kept.
