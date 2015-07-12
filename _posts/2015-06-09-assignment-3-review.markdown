---
layout: post
title:  "Assignment 3 review. Students database"
date:   2015-06-09 09:00:00
category: assignments
tags:
    - training
    - assignment
    - students database
    - review
excerpt: |
    Students database.
    Review results. Common mistakes, ideas to improve and notes about this assignment.
---
* TOC
{:toc}

## Received assignments.

* https://github.com/panayotovyura/project4

* https://github.com/alex-kalenyuk/students_db

* https://github.com/dhalkin/students

## PHP.

* Garbage collector

## Symfony.

* No need to use all standard bundles. Just disable them and some memory & CPU time

* Try to decouple your services

* Pass as more specific classes as possible as dependencies into your services

* 2.7 is available now!

## Doctrine.

* Put your custom queries into repository classes

## Unit tests.

* Use @dataproviders

* Test all possible input chars in unit tests

* It's ok to use negative test cases