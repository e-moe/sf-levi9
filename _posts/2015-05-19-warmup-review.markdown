---
layout: post
title:  "Warmup assignment review"
date:   2015-05-19 18:00:00
category: assignments
tags:
    - training
    - assignment
    - warmup
    - review
excerpt: |
    Recycle batteries.
    Review results. Common mistakes, ideas to improve and notes about this assignment.
---
* TOC
{:toc}

## Composer.

* You don't need to upload vendor folder. Put it to your ".gitignore" file. Upload only "composer.json" and
   "composer.lock" files.

* Add real "name" and "description" fields.

* Update/add "php" version in "require" section and used extensions.

* Use "github-oauth" token ([details][composer-gh-token])

## Symfony.

* Try to omit deprecated functions (e.g. "$this->getDoctrine()->getEntityManager()")

* Name your controllers correctly

## Forms.

* Do not add submit buttons into form types ([details][sf-forms-buttons])

## Doctrine.

* Do not use Entity manager if possible

## Functional tests.

* Tests should be able to run multiple times.

* Test functions should be atomic.

* It's better to use short selectors.

[composer-gh-token]:        https://getcomposer.org/doc/articles/troubleshooting.md#api-rate-limit-and-oauth-tokens
[sf-forms-buttons]:         http://symfony.com/doc/current/best_practices/forms.html#form-button-configuration