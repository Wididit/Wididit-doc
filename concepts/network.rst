.. _concepts-network:

*******
Network
*******

Obviously, a Wididit network is a network of Wididit server. What does it
mean?

Some rare existing social networks call themselves distributed. However,
they are not as much distributed as Wididit is.

Establish a connection
======================

When you connect two servers together, both of them ask the other for a list
of all servers of its network (ie. all servers it is connected to).
Generally, one of them already belongs to a network (probably the main
Wididit network), and the other one is a newly created server. In such
a case, the new one will get a list of all servers of the main network,
and all servers of the main network will connect to this network.

This might sound dangerous: so much connections at once! Thanksfully, a
connection is a quite simple procedure:

* Add each other to its own network
* Query each other its network

and that's all.

As all networks are connected to all other networks, there are no hubs or
weak links. Netsplits are cool, but only on IRC.

What a connection is really
===========================

Once connected, people from the both networks can subscribe to other located
on the other side of the "gap", and send them messages.

All people are identified by a unique ID: username@servername.tld, where
servername.tld is the server hostname.
