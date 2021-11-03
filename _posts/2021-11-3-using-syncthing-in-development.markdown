---
layout: post
title:  "Experimenting with Hacking on FreeBSD Using Syncthing"
date:   2021-11-3 12:00:00 -0700
categories: freebsd development 
---

I like to use several different machines whilst hacking on FreeBSD.  The fasted machine in my home is the desktop in my home office that runs Linux (for bluetooth headphones and Steam).

I hack on FreeBSD inside a virtual machine on this box since it has 24 cores and lots of RAM.  I also enjoy going someplace outside of the house to code like the library or a coffee shop since my home is chock-full of distracting people and animals.

My basic process goes like this:  update FreeBSD code on laptop, desktop, or wherever and compile on fast VM in home office.  I've been using github to sync around copies of the FreeBSD source tree and update feature branches over time but that has a few limitations. 

Namely, it's easy for the code to become unsync'd since some code I'm writing is commited to the branch but sometimes it isn't (like tests, proof of concepts, etc).  I'd rather have my entire development environment with me wherever I go.  [Syncthing](www.syncthing.net) appers to fit the bill for that use case.

With syncthing, everyhing I write is sync'd around to the various systems that have access to my freebsd-src repository.  This way, I can write quick test scripts on my macbook using mac based editors and actually run them in the VM as soon as they're synced.  Or when I'm sitting at my desk in my home office on my Linux desktop updating code and it gets modified in realtime in the VM.

There are some gotchas to using this method of development synchronization, however.

First, it breaks the concept of a distributed source code revision system and all the inherent benefits that goes along with it.  Every little change you make is propagated to all of your systems instead of having completely seperate codebases.  Switching a branch on a repo that's syncthing'd also switches the branch on all syncthing'd systems.

Second, big changes (such as pulling new changes from github) can result in a synchronization that takes some time to complete all the while your git repository isn't functional on the syncthing'd hosts.

So, like I said, this is all just an experiment.  I'm not sure how long I'll use this syncing methodology.  If I get too annoyed with this method, I'll just jump back to using github.

Ideally, I'd just develop on a fast desktop system that already has FreeBSD installed.

That's how I did things for a long time but needed something else after re-installing my desktop with Linux (again, see bluetooth and video games).

I think the correct solution is to build a PC for gaming only but that requires mucho monies so for now I'll keep on syncing.
