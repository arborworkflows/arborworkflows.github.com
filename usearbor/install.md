---
layout: home
title: "Install Arbor"
date: 2017-05-15
modified:
excerpt:
tags: []
image:
  feature:
  teaser:
  thumb:
share: false
---

## Local Arbor installation

The instructions below are the simplest way to get an Arbor instance up and going on your own personal machine - although they should work equally well for getting things going on a server. If you want more detail about how to install the individual parts of Arbor, you can also go to our “readthedocs” pages created and maintained by Kitware.

It is also worth noting that you can run Arbor without installing it locally. In fact, Arbor is made to run over the web - and perhaps one of our running Arbor instances can already serve you?

We will post instructions on how to install an Arbor instance remotely using AWS or Cy-Verse.

### Prerequisites

To install Arbor locally, you need the following three programs - each of which might have some dependencies of its own. All three are free and open source.

First, you need [VirtualBox](https://www.virtualbox.org/), the method we use to create and host virtual machines. You can download and install VirtualBox using the link on their webpage.

Second, you need [Ansible](https://www.ansible.com/), the manager that decides which software gets installed on your virtual machine. [Installation instructions for Ansible](http://docs.ansible.com/ansible/intro_installation.html)

Finally, you need [Vagrant](https://www.vagrantup.com/), which manages the whole process.

### Step 1: Get the "Flow"

To begin, clone the two github repos that you will need: the [Flow repo](https://github.com/kitware/flow) from [Kitware](https://www.kitware.com/), which has all that you need to set up an empty Arbor instance; and the [arborCollections](https://github.com/arborworkflows/arborcollections) repo, which has all of the basic Arbor collections you will need.

To clone these two repositories, use "git clone". [Further instructions for using git clone](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)

### Step 2: Launch Arbor

Now, you will launch your arbor instance. In the terminal, navigate to your local copy of the flow repository. If you just cloned the repo, then:

`cd flow`

Now, launch Vagrant, which will use Ansible and VirtualBox to set up your Arbor instance.

`vagrant up`

Now you wait. This might take a while - perhaps even 20 minutes or so!

When the whole process is finished, you should see a success message.

````
PLAY RECAP *********************************************************************
flow                       : ok=75   changed=56   unreachable=0    failed=0   
````

Now you can visit your Arbor instance by opening a web browser (we recommend Chrome) and navigating to:

[http://localhost:8080/](http://localhost:8080/)

You should see a brand-new empty Arbor instance:

![arbor-empty]({{site.baseurl}}/images/install-1.png)

### Step 3: Install Arbor collections

To do this, you will need to obtain the current arbor collections from github; then those collections can be loaded into Girder, which manages the functions, data, and users in Arbor.

First, ssh into your virtual machine.

`vagrant ssh`

You will see a login message and then a command prompt:

````
Welcome to Ubuntu 14.04.5 LTS (GNU/Linux 3.13.0-117-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Mon May 15 16:32:29 UTC 2017

  System load:  0.11              Processes:           95
  Usage of /:   9.3% of 39.34GB   Users logged in:     0
  Memory usage: 15%               IP address for eth0: 10.0.2.15
  Swap usage:   0%

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

New release '16.04.2 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Mon May 15 16:32:29 2017 from 10.0.2.2
vagrant@vagrant-ubuntu-trusty-64:~$
````

Now clone the arborCollections github repository into that directory.

`git clone https://github.com/arborworkflows/arborCollections.git`

You should get this result:

````
vagrant@vagrant-ubuntu-trusty-64:~$ git clone https://github.com/arborworkflows/arborCollections.git
Cloning into 'arborCollections'...
remote: Counting objects: 6784, done.
remote: Total 6784 (delta 0), reused 0 (delta 0), pack-reused 6784
Receiving objects: 100% (6784/6784), 99.45 MiB | 12.99 MiB/s, done.
Resolving deltas: 100% (3613/3613), done.
Checking connectivity... done.
vagrant@vagrant-ubuntu-trusty-64:~$
````

Finally, run a python script that loads these analyses into Arbor:

`python /vagrant/devops/load-analysis.py ./arborCollections`

You will see analyses being loaded into Arbor:

````
Merge Tree, Occurrences, and Morphology.json successfully uploaded to advanced-phylomap
LifeMapper occurrences from Experiment Number.json successfully uploaded to advanced-phylomap
Explore LifeMapper occurrences from Experiment Number.json successfully uploaded to advanced-phylomap
Return LifeMapper occurrences from Experiment Number Table.json successfully uploaded to advanced-phylomap
````

And so on...

Now, when you go back to your Arbor instance at [http://localhost:8080/](http://localhost:8080/), you will see all the analyses loaded:

![arbor-loaded]({{site.baseurl}}/images/install-2.png)

Now you are ready to do things in Arbor!
