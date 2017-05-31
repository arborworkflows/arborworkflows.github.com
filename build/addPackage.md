---
layout: page
title: Add packages to Arbor
permalink: /build/addPackage.html
---

Adding new R packages or python libraries to Arbor is not difficult, but the method you use depends on the type of Arbor instance you are using.

## New packages on Arbor AWS instances

If you are using one of our [AWS instances]({{site.baseurl}}/usearbor/aws-instances/), then the only way to add new R packages is to [contact us]({{site.baseurl}}/team/). We can get things installed for you quickly and easily, but it requires administrative access to the instance.

## New packages on locally installed AWS instances

### Local installation using ssh

If you have an Arbor instance on a local machine, you have two options. First, you can ssh into the instance and install the R package.

To get into the vagrant machine use:

```
vagrant ssh
```

You should see something like:

```
Lukes-MacBook-Pro:flow lukeharmon$ vagrant ssh
Welcome to Ubuntu 14.04.5 LTS (GNU/Linux 3.13.0-117-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Wed May 31 20:12:04 UTC 2017

  System load:  0.0               Processes:           95
  Usage of /:   9.1% of 39.34GB   Users logged in:     0
  Memory usage: 10%               IP address for eth0: 10.0.2.15
  Swap usage:   0%

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

28 packages can be updated.
16 updates are security updates.

New release '16.04.2 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Wed May 31 20:12:05 2017 from 10.0.2.2
vagrant@vagrant-ubuntu-trusty-64:~$
```

Now start R. You will need administrative privileges, so:

```
sudo R
```

This starts an R environment.

```
vagrant@vagrant-ubuntu-trusty-64:~$ sudo R

R version 3.4.0 (2017-04-21) -- "You Stupid Darkness"
Copyright (C) 2017 The R Foundation for Statistical Computing
Platform: x86_64-pc-linux-gnu (64-bit)

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under certain conditions.
Type 'license()' or 'licence()' for distribution details.

  Natural language support but running in an English locale

R is a collaborative project with many contributors.
Type 'contributors()' for more information and
'citation()' on how to cite R or R packages in publications.

Type 'demo()' for some demos, 'help()' for on-line help, or
'help.start()' for an HTML browser interface to help.
Type 'q()' to quit R.

>
```

Now I can install any package I want. For example:

```
install.packages("ouch")
```

You should get something like:

```
> install.packages("ouch")
Installing package into ‘/usr/local/lib/R/site-library’
(as ‘lib’ is unspecified)
trying URL 'https://cran.cnr.berkeley.edu/src/contrib/ouch_2.9-2.tar.gz'
Content type 'application/x-gzip' length 37358 bytes (36 KB)
==================================================
downloaded 36 KB

* installing *source* package ‘ouch’ ...
** package ‘ouch’ successfully unpacked and MD5 sums checked
** libs
gcc -std=gnu99 -I/usr/share/R/include -DNDEBUG      -fpic  -g -O2 -fstack-protector --param=ssp-buffer-size=4 -Wformat -Werror=format-security -D_FORTIFY_SOURCE=2 -g  -c covar-matrix.c -o covar-matrix.o
gcc -std=gnu99 -I/usr/share/R/include -DNDEBUG      -fpic  -g -O2 -fstack-protector --param=ssp-buffer-size=4 -Wformat -Werror=format-security -D_FORTIFY_SOURCE=2 -g  -c weight-matrix.c -o weight-matrix.o
gcc -std=gnu99 -shared -L/usr/lib/R/lib -Wl,-Bsymbolic-functions -Wl,-z,relro -o ouch.so covar-matrix.o weight-matrix.o -L/usr/lib/R/lib -lR
installing to /usr/local/lib/R/site-library/ouch/libs
** R
** data
** inst
** preparing package for lazy loading
** help
*** installing help indices
** building package indices
** testing if installed package can be loaded
* DONE (ouch)

The downloaded source packages are in
	‘/tmp/RtmpCawCDV/downloaded_packages’
>
```

Now you can use this package in your Arbor functions!

If you use this method, then the packages will be installed on that virtual machine for as long as it lasts. However, if you destroy or reprovision that machine, then the packages will have to be reinstalled. For something more permanent, try the next method.

### Adding new packages to the virtual machine

You can determine which R packages are installed on an Arbor instance using Vagrant and ansible.

When you launch a new Arbor instance, one step involves cloning the [github repository that holds Kitware's "flow" software](https://github.com/kitware/flow).

In your local clone of that repository, find the file ./devops/ansible/roles/arbor/tasks/main.yml. The Kitware default version is [here](https://github.com/Kitware/flow/blob/master/devops/ansible/roles/arbor/tasks/main.yml).

R packages to be installed are listed starting on line 42 of that file:

```

- name: install packages
  command: /usr/bin/Rscript --slave --no-save --no-restore-history -e "if (! ('{{ item }}' %in% installed.packages()[,'Package'])) install.packages(pkgs='{{ item }}', repos=c('http://cran.cnr.Berkeley.edu'))"
  become: yes
  with_items:
    - rgl
    - ape
    - geiger
    - nlme
    - codetools
    - devtools
    - diversitree
    - phytools
    - dplyr
  environment:
    DISPLAY: :7


- name: install github packages
  command: /usr/bin/Rscript --slave --no-save --no-restore-history -e "parts<-unlist(strsplit('{{ item }}', '/'));options(repos='http://cran.cnr.Berkeley.edu');library(devtools);install_github(parts[2], parts[1])"
  become: yes
  with_items:
    - hafen/cardoonTools
    - tangelo-hub/romanescoTools
    - arborworkflows/aRbor
  environment:
```

New packages can be added to that list and will be installed when the machine is provisioned.

So, add ouch:

```
- name: install packages
  command: /usr/bin/Rscript --slave --no-save --no-restore-history -e "if (! ('{{ item }}' %in% installed.packages()[,'Package'])) install.packages(pkgs='{{ item }}', repos=c('http://cran.cnr.Berkeley.edu'))"
  become: yes
  with_items:
    - rgl
    - ape
    - geiger
    - nlme
    - codetools
    - devtools
    - diversitree
    - phytools
    - dplyr
    - ouch
  environment:
    DISPLAY: :7
```

And reprovision:

```
> vagrant provision
```
