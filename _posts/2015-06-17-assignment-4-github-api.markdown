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
    Idea of GitHub API is to create RESTful webservice proxy for GitHub API with additional functionality.
---
* TOC
{:toc}

## GitHub API.

Idea of GitHub API is to create RESTful webservice proxy for [GitHub API][api-doc] with additional functionality.
It&nbsp;should be possible to get list of your repositories (filtered) from GitHub and provide additional comments list.

![HitHub API][github_api]

## 1. API v1: Implement basic GitHub service.

Create service class in your application for [GitHub API][api-doc] connection. The only data you need -
[list][api-repos] of user's repositories.

**Tip:** _Use [Guzzle][guzzle] HTTP Client library or one of available Guzzle Bundles._

{% highlight php %}
GET /repos?[page=:x&per_page:y]
{% endhighlight %}

## 2. API v2: Implement comments service.

{% highlight php %}
GET         /repos?[type=all|owner|public|private|member][page=:x&per_page:y]
GET|POST    /repos/:name/comments?[page=:x&per_page:y]
GET|PUT     /repos/:name/comments/:id
{% endhighlight %}

## 3. API v3: Auth, formats and HATEOAS.

Support Auth and multiple users, data formats: JSON and XML and links HATEOAS.

{% highlight php %}
GET         /repos?[type=all|owner|public|private|member][page=:x&per_page:y]
GET|POST    /repos/:name/comments?[page=:x&per_page:y]
GET|PUT     /repos/:name/comments/:id
{% endhighlight %}

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
[github_api]:           {{ site.baseurl }}/assets/github_api.png
[api-doc]:              https://developer.github.com/v3/
[api-repos]:            https://developer.github.com/v3/repos/
[guzzle]:               http://guzzle.readthedocs.org/en/latest/
[phpunit]:              https://phpunit.de/
[phpcs]:                https://github.com/squizlabs/PHP_CodeSniffer
[psr2]:                 https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md
[phpmd]:                http://phpmd.org/
[phpcpd]:               https://github.com/sebastianbergmann/phpcpd
[travis-ci]:            https://travis-ci.org/
[travis-ci-gs]:         http://docs.travis-ci.com/user/getting-started/
[travis-ci-php]:        http://docs.travis-ci.com/user/languages/php