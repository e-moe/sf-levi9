---
layout: post
title:  "Assignment 1 review. Sport calendar"
date:   2015-05-25 18:00:00
category: assignments
tags:
    - training
    - assignment
    - calendar
    - review
excerpt: |
    Sport calendar.
    Review results. Common mistakes, ideas to improve and notes about this assignment.
---
* TOC
{:toc}

## Received assignments.

* https://github.com/panayotovyura/project2

## Composer.

* Update/add "php" version in "require" section and used **extensions**

* Use "github-oauth" token ([details][composer-gh-token])

* Try to avoid unstable requirenments (e.g. "dev-maser" or "@dev")

## Fixtures.

* Store seed value in config.yml file

* Ideally, DataFixtureLoader should only return fixtures.yml file. Try to avoid custom extensions.

{% highlight php %}
description: <randomElement(['Chest Press', 'Biceps Curl', 'Front Lunge', ...])>
{% endhighlight %}

## Symfony.

* Always use keys for translations instead of content strings. ([details][sf-bp-keys])

* Use Symfony IDE integration (e.g PHP Storm [integration][phpstorm-integration])

## Routing.

* Add "_locale" prefix only once routing.yml

## Security.

* Do not check user in controller and do not redirect to login page. It should be handled automatically by Symfony.

## Twig.

* Do not add logic into view files.

## Doctrine.

* No need to create empty repository files.

## Unit tests.

* Tests should be able to run multiple times

* Test functions should be atomic

[composer-gh-token]:        https://getcomposer.org/doc/articles/troubleshooting.md#api-rate-limit-and-oauth-tokens
[sf-bp-keys]:               http://symfony.com/doc/current/best_practices/i18n.html
[phpstorm-integration]:     https://confluence.jetbrains.com/display/PhpStorm/Symfony+Development+using+PhpStorm