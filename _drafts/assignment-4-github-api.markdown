---
layout: post
title:  "Assignment 4. GitHub API"
date:   2015-06-17 18:00:00
category: assignments
tags:
    - training
    - assignment
    - github api
    - api
    - rest
excerpt: |
    GitHub API.
    Idea of ...
---
* TOC
{:toc}

## GitHub API.

Idea of GitHub API is to create ...

## 1. API v1: Implement basic GitHub service.

GET /repos?[page=:x&per_page:y]

## 2. API v2: Implement comments service.

GET         /repos?[type=all|owner|public|private|member][page=:x&per_page:y]
GET|POST    /repos/:name/comments?[page=:x&per_page:y]
GET|PUT     /repos/:name/comments/:id

## 3. API v3: Auth, formats and HATEOAS.

JSON and XML, HATEOAS

GET         /repos?[type=all|owner|public|private|member][page=:x&per_page:y]
GET|POST    /repos/:name/comments?[page=:x&per_page:y]
GET|PUT     /repos/:name/comments/:id
 
## 4. Write unit tests.

Write unit tests to cover GitHub and Comments services usage [PHPUnit][phpunit].

## 5. Static Analysis Tools (optional).

Update your "composer.json" "require-dev" section to install these tools:

* [PHP_CodeSniffer][phpcs] (Use [PSR2][psr2] coding style guide rules set)
* [PHP Mess Detector][phpmd]
* [PHP Copy/Paste Detector][phpcpd]

Check your "src/" folder and fix as much errors/warnings as possible.
  
## 6. Integrate Travis CI (optional).
 
Integrate continuous integration (CI) into your repository based on [Travis CI][travis-ci]
([Getting started][travis-ci-gs], [PHP][travis-ci-php]).
 
* Register in Travis CI (preferable using [GitHub][github] account)
* Add your repository
* Create ".travis.yml"
* Test your integration

## 7. Share your code.

Commit your latest code into [GitHub][github] and send the link as a result of fulfilled home task.

[github]:               https://github.com/
[phpunit]:              https://phpunit.de/
[phpcs]:                https://github.com/squizlabs/PHP_CodeSniffer
[psr2]:                 https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md
[phpmd]:                http://phpmd.org/
[phpcpd]:               https://github.com/sebastianbergmann/phpcpd
[travis-ci]:            https://travis-ci.org/
[travis-ci-gs]:         http://docs.travis-ci.com/user/getting-started/
[travis-ci-php]:        http://docs.travis-ci.com/user/languages/php