Experimenting with Developing FreeBSD and Syncthing
==

I like to use several different machines whilst hacking on FreeBSD.

My fasted machine in my home is my desktop in my home office that runs Linux (for bluetooth speakers and games).

I compile FreeBSD inside a virtual machine on my Linux box that has 24 cores and lots of RAM.

I also enjoy going someplace outside of the house to code like the library or a coffee shop since my home is chaulk full of people and animals.

So the basic requirement is, update FreeBSD code on laptops, desktops, or wherever and compile on fast VM in home office.

I've been using github to sync around copies of the FreeBSD git tree and updating feature branches but that has a few limitations.

It's easy to get de-sync'd since some code I'm writing is necessarily commited to the branch, like simple tests.

I'd rather have my entire development environment with me wherever I go.

Syncthing seems to fit the bill for that.

Everyhing I write is sync'd around to the various systems that have access to my freebsd-src repository.

That way, I can write quick test scripts on my macbook using mac based editors and actually run them in the VM.

Or when I'm sitting at my desk in my home office on my Linux desktop updating code and it gets modified in realtime in the VM.

There are some gotchas to using this method of development synchronization.

First, it breaks the concept of a distributed source code revision system.

Every little change you make is propagated to all of your systems so you don't have different systems

Second, big changes (such as pulling new changes from github) can result in a synchronization that takes a little bit all the while your git repository isn't functional.

Currently, this is all just an experiment.

I'm not sure how long I'll use this syncing methodology.

Ideally, I'd just develop on a fast desktop system that already has FreeBSD installed.

That's how I did things for a long time but needed something else after re-installing my desktop with Linux (again, see bluetooth and video games).

