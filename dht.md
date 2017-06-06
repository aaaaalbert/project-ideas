# Implement distributed `advertise` methods for Seattle

### Overview
In this project, you investigate *Distributed Hash Tables (DHTs)*
that are used in peer-to-peer software like BitTorrent to advertise
and look up data. Based on an understanding of the concept, you design a
[RepyV2](https://github.com/SeattleTestbed/repy_v2/README.md)
library that interfaces Seattle's
[advertising library](https://github.com/SeattleTestbed/seattlelib_v2/blob/master/advertise.r2py)
with, for example, the [Kademlia](https://en.wikipedia.org/wiki/Kademlia)
Distributed Hash Table (DHT) advertise/lookup system.


### Background
Key-value stores are a simple yet powerful concept to associate some
data (the value) with an index (the key). Whoever knows the key can
look up the value at the key-value store; to store some data, you
provide both the key and value. Depending on the actual implementation,
newly announced values for the same key override or augment one another;
values might time out and be removed from the store (as with DNS);
there might be multiple key-value stores that store only parts of the
key space; etc.

Seattle Testbed currently uses multiple *centralized* key-value stores
(called "advertise services" in that context)
to advertise and look up information. For example, a Seattle node
advertises the public keys to identify the users that can control it
(as the *key*), and their IP address and port number (as the *value*).
Using the public key, the experiment manager `seash` can find the
node's address from the advertise services.

**(...to-do: add a short intro into the concept; for now just
take a look at https://en.wikipedia.org/wiki/BitTorrent_tracker ...)**


### Your Task
Take a look at, e.g., @mwarning's [`kadnode` project](https://github.com/mwarning/kadnode/),
to see a practical implementation of a protocol bridge between
two methods of performing look-ups. Identify the logical flow of
information between a lookup request in one protocol (DNS) and the
actual DHT lookup that is triggered from this.
You might want to use `kadnode` as a reference lookup tool
while you work on your RepyV2 implementation.

Split your implementation into a look-up and an announcement part.
Start with whatever you think is easier to tackle --- and easier
to test.
At the end of your project, we would like to have a usable, tested
RepyV2 library for using DHTs to announce and look up information
pertaining to the operation of Seattle nodes.



### Milestones And Deliverables (meta-information)
1. Make a plan, describe what you will do, and when you will do it.
  Do this on a public GitHub repo.
2. If you are a summer research student, follow NYU's requirements
  for handing in an abstract and project description, attending the
  poster presentation, etc.
3. Share all code and data, notes, plans, online so that your supervisors
  can view and comment on them. Attend the regular group/individual meetings,
  see [the top-level README](README.md) for details.


