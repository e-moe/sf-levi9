---
layout: post
title:  "Assignment 2 review. Jam storage"
date:   2015-06-02 09:00:00
category: assignments
tags:
    - training
    - assignment
    - jam storage
    - review
excerpt: |
    Jam storage.
    Review results. Common mistakes, ideas to improve and notes about this assignment.
---
* TOC
{:toc}

## Received assignments.

* https://github.com/panayotovyura/project3

* https://github.com/alex-kalenyuk/jam_storage

* https://github.com/dhalkin/jam

## Composer.

* Keep composer up to date

* Try to avoid unstable requirements (e.g. "dev-maser" or "@dev")

## Travis-ci.

* Composer self-update

* Code quality checks

* For real unit tests you not even need db

## Fixtures.

* Use "(unique)" values

* Use range generations

* Use optional values (e.g. 50%?)

## Symfony.

* Try to decouple your services

* Pass as more specific classes as possible as dependencies into your services.

* 2.7 is available now!

## Doctrine.

* Use appropriate types

## Unit tests.

* The only one real class in your tests - is tested class. Other ones - mocks.

* No need to load all symfony kernel with services, no need to write functional tests (in this task)

* Unit tests is **much** faster then functional ones

* Cover all logic with unit tests and happy flow with functional

* Tests should be able to run multiple times

* Test functions should be atomic