---
layout: post
title:  "Assignment 2. Jam storage"
date:   2015-05-27 18:00:00
category: assignments
tags:
    - training
    - assignment
    - jam storage
    - sonata
excerpt: |
    Jam storage.
    Idea of Jam storage – is a web application that keeps information about all jars of jam stored at home.
    When one receives from a granny few jars of strawberry jam – he adds information about them into database.
    Sonata Admin Bundle usage, static code quality checks and Travis CI integration.
---
* TOC
{:toc}

## Jam storage.

Idea of Jam storage – is a web application that keeps information about all jars of jam stored at home.

![Jam jars][jam-jars]

When one receives from a granny few jars of strawberry jam – he adds information about them into database.
It is possible to write amount of jars, type of jam, year of production and some comment.

Then later, when some jar of jam is eaten away, there is possibility to remove one jar from storage.

And after sweet meal, one can have an overview of jams he didn’t eat yet. ☺

## 1. Create data model and fill it with fixtures.

Data model consists of 2 enumerations (jam type, year of production) and JamJar entity.

Enumerations are simple entities with id + name fields.

JamJar entity has next fields: jam type (single select), year (single select), comment (text, optional).

Please, create few values for enumerations and few JamJar instances via [Alice][alice] fixtures.

**Tip:** _Use [SQLite][sqlite] for additional experience and respect ☺._

## 2. Set up Sonata Admin Bundle.

Set up bundle and implement CRUD for enumerations. Use [documentation][sonata] for help.

## 3. Implement CRUD for JamJar entity.

Use [documentation][sonata] for help.

## 4. Amount functionality

Add to the form of JamJar "Ammount" field. This field should be available only on "create" form.
This field is not mapped to entity. By default value of field is 1. If during creation of JamJar user
changes value to N – then during creation, N instances of JamJar should be created.

## 5. Write unit tests

It would be nice if this multiplying/copying logic would be stored in a service class and covered with unit test
([PHPUnit][phpunit]).

## 6. Static Analysis Tools.

Update your "composer.json" "require-dev" section to install these tools:

* [PHP_CodeSniffer][phpcs] (Use [PSR2][psr2] coding style guide rules set)
* [PHP Mess Detector][phpmd]
* [PHP Copy/Paste Detector][phpcpd]

Check your "src/" folder and fix **all** errors/warnings.
  
## 7. Integrate Travis CI
 
Integrate continuous integration (CI) into your repository based on [Travis CI][travis-ci]
([Getting started][travis-ci-gs], [PHP][travis-ci-php]).
 
* Register in Travis CI (preferable using [GitHub][github] account)
* Add your repository
* Create ".travis.yml"
* Test your integration

## 8. Share your code.

Commit your latest code into [GitHub][github] and send the link as a result of fulfilled home task.

[jam-jars]:             {{ site.baseurl }}/assets/jam_jars.jpg
[sonata]:               https://sonata-project.org/bundles/admin
[alice]:                https://github.com/hautelook/AliceBundle
[github]:               https://github.com/
[phpunit]:              https://phpunit.de/
[phpcs]:                https://github.com/squizlabs/PHP_CodeSniffer
[psr2]:                 https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md
[phpmd]:                http://phpmd.org/
[phpcpd]:               https://github.com/sebastianbergmann/phpcpd
[travis-ci]:            https://travis-ci.org/
[travis-ci-gs]:         http://docs.travis-ci.com/user/getting-started/
[travis-ci-php]:        http://docs.travis-ci.com/user/languages/php
[sqlite]:               https://www.sqlite.org/