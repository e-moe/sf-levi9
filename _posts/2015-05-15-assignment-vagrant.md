---
layout: page
title: Assignment. Vagrant - Developing complex environments locally
date:   2015-05-15 13:00:00
category: vagrant
tags:
    - training
    - assignment
    - vagrant
excerpt: |
    How to use Vagrant during complex web applications development? In this assigment we will use Vagrant to create
    three virtual machines: 2 identical PHP nodes and 1 load balancer.
---
* TOC
{:toc}

## Multiple PHP nodes through load balancer with shared session.

Idea of this workshop is to learn how to use Vagrant during complex web applications development. In this task
we will create three virtual machines: 2 identical PHP nodes and 1 load balancer.

## Technical details.

- Load balancer
    * Nginx (load balancer)
    * MySQL database (db + session storage)

- PHP nodes
    * Apache (web server)
    * PHP
    * Symfony application with shared session (see above)

![vagrant][vagrant_schema]

## Implementation.

1. Initialize Vagrant project.
    * Open empty folder and run: vagrant init [[1](#1)].

2. Edit Vagrantfile generic parameters.
    * Fill in box name (e.g. ubuntu/trusty64) [[2](#2)] and virtual box parameters: RAM size and number of CPU
      (e.g. 512 MB and 1 CPU) [[3](#3)].

3. Create config for two PHP node machines [[4](#4), [5](#5)].
    * Create shell script for provision (install apache, php, create VirtualHost configuration and run
      Symfony console commands) [[6](#6), [7](#7)];
    * Setup “private_network” with predefined IP addresses (192.168.50.1x) [[8](#8)];
    * Create Symfony project in subdirectory [[9](#9)];
    * Make this folder synchronized with virtual machines [[10](#10)].

4. Test node virtual machines configuration.
    * Run vagrant up node-1 and check Symfony app in browser (http://192.168.50.10/). Repeat the same for node-2.

5. Create config for load-balancer [[4](4), [5](5)].
    * Create shell script for provision (install nginx, mysql and service configuration files) [[6](6), [11](11)];
    * Setup “private_network” with predefined IP addresses (192.168.60.10) [[8](8)];
    * Fill in Symfony Trusting proxies [[12](12)].

6. Test load-balancer virtual machine configuration.
    * Run vagrant up load-balancer and check that nginx serving backend nodes for you (http://192.168.60.10/).

7. Update Symfony application.
    * Move session into load-balancer database; [[13](13)]
    * Update secured actions to show current backend server IP.

8. Final checks.
    * Run vagrant destroy to remove all virtual machines;
    * Run vagrant up without additional parameters to start all virtual machines;
    * Test application in your browser (http://192.168.60.10/) – it should be possible to login, access restricted area,
      and see different IP addresses on page reload (session should be preserved, user should remain logged in).

## Useful documentation.

1. <a name="1"></a> https://docs.vagrantup.com/v2/getting-started/index.html
2. <a name="2"></a> https://docs.vagrantup.com/v2/getting-started/boxes.html
3. <a name="3"></a> https://docs.vagrantup.com/v2/virtualbox/index.html
4. <a name="4"></a> https://docs.vagrantup.com/v2/multi-machine/index.html
5. <a name="5"></a> https://docs.vagrantup.com/v2/vagrantfile/tips.html
6. <a name="6"></a> https://docs.vagrantup.com/v2/provisioning/shell.html
7. <a name="7"></a> http://httpd.apache.org/docs/2.2/vhosts/examples.html
8. <a name="8"></a> https://docs.vagrantup.com/v2/networking/private_network.html
9. <a name="9"></a> http://symfony.com/doc/current/book/installation.html
10. <a name="10"></a> https://docs.vagrantup.com/v2/synced-folders/basic_usage.html
11. <a name="11"></a> http://nginx.org/en/docs/http/load_balancing.html
12. <a name="12"></a> http://symfony.com/doc/current/components/http_foundation/trusting_proxies.html
13. <a name="13"></a> http://symfony.com/doc/current/cookbook/configuration/pdo_session_storage.html

## Attachments.

* [Workshop presentation (pptx)][vagrant_pptx]

[vagrant_schema]:    {{ site.baseurl }}/assets/vagrant.png
[vagrant_pptx]:      {{ site.baseurl }}/assets/vagrant.pptx