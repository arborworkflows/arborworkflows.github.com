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


### Step 3: Install Arbor collections
