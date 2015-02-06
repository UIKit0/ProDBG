---
layout: post
title: First post 
---


Switching from TeamCity to Buildbot
-----------------------------------

I have been using TeamCity http://www.jetbrains.com/teamcity for ProDBG now for a while and while it has serverd me well I ran into the limit of 3 agents on the free version. While I certanly can affort to pay for a few extras it just doesn't feel right to do that and if I want to add more machines the costs will rise even more and I don't feel I want to be restricted to the amount of machines I can have.

In my TeamCity setup I have 3 agents which is for Mac, Windows and Linux. They all build code but does some different things as well:

* Mac: Build code, run tests, start ProDBG
* Windows: Bulid code, run tests, run PCLint
* Linux: Build code, run tests

They all send mail in case some of the steps are broken.
