---
layout: post
title: First post 
---


Switching from TeamCity to Buildbot
===================================

I have been using TeamCity http://www.jetbrains.com/teamcity for ProDBG now for a while and it has serverd me well but I ran into the limit of 3 agents on the free version. While I certanly can affort to pay for a few extras it just doesn't feel right to do that and if I want to add more machines the costs will rise even more and I don't feel I want to be restricted to the amount of machines I can have.

In my TeamCity setup I have 3 agents which is for Mac, Windows and Linux. They all build code but does some different things as well:

* Mac: Build code, run tests, start ProDBG
* Windows: Bulid code, run tests, run PCLint
* Linux: Build code, run tests

They all send mail in case some of the steps are broken and that is my basic use case.

Buildbot is an open source project which is used for many projects. It's more of a framework that you build your buildsystem around but it's still easy to get going quite fast.

One thing to notice. Buildbot uses *Master* and *Slave* as lingo for describing the buildprocess. Some people find these terms offensive and I prefer the terms *Coordinator* and *Agent*. In this article I will use my terms *except* when I need to describe actual commands for Buildbot.

The current latest released version of Buildbot is 0.8.11 but I decided to go for the latest head version (and all the issues that comes with) that because of many improvements that has been done esp to the web UI that is used on the *Coordinator* to display the status of the builds.

Getting started
---------------

I will outline the steps I took to get everything up and running so this will read a bit like a tutorial but depending on your OS your millage may wary. I set up the *Coordinator* and a Mac and also added build *Agents* on another Mac and a Windows machine.

Getting the code.

```
git clone https://github.com/builbot/buildbot.git
```

Getting the *Coordinator* up and running

```
cd buildbot/master
python setup.py install

```

Notice that after this step. I ran into some issues which was usually quite easy to solve. For example npm wasn't installed and I just used brew to install this.

```
brew install npm
```

Next step is to create


