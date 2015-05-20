---
layout: post
title:  "Assignment 1. Sport calendar"
date:   2015-05-20 09:00:00
category: assignments
tags:
    - training
    - assignment
    - calendar
excerpt: |
    Sport calendar.
    Idea of sport calendar – is a web application, which helps athletes to track their progress in gym.
    When athlete finishes an exercise – he came to our site to save the information. For example, he writes that he did
    press of a bar 8 times with weight 100kg. This data together with timestamp is savedto database.
---
* TOC
{:toc}

## Sport calendar.

Idea of sport calendar – is a web application, which helps athletes to track their progress in gym.

When athlete finishes an exercise – he came to our site to save the information. For example,
he writes that he did press of a bar 8 times with weight 100kg. This data together with timestamp is saved to database.

Then, on a dashboard athlete sees:

* what exercises he did today,
* what he did a week ago (on the same weekday),
* what he did 2 weeks ago.

In current task we will create only dashboard. There will be fixtures that add data for testing purpose,
so we do not need any form to add exercises.

So, go throw steps:

## 1. Create new Symfony project on GitHub.

Create open source project on [GitHub][github] to commit your code for this assignment.

## 2. Create data model and fill it with fake data.

There is only one entity - Exercise. Fields are: short description of done exercise, weight,
count of times exercise was done, date, time (here it’s better to store date without time, it’ll simplify logic later).

**Tip:** _You could use build-in code generators to generate a bundle and an entity._

Then you have to fill data model with fake data (for testing). There is excellent tool for this -
[Nelmio Alice bundle][alice]. Create following fixtures: 3 types of exercises (3 different short descriptions) are
randomly imploded into dates of last 30 days, including today. Weight is random between 20 and 200kg.
Count of times – is also random, 5-15. Total amount of exercises done in last 30 days should be about 300-400.

## 3. Implement Front-end.

Dashboard should be very simple – just some title and table with 3 columns:

![Calendar table][calendar_table]

If this project is success, it will require a mobile application with the same dashboard. So, all data should be fetched
via service layer, to be reused later.

**Tip:** _Try to implement this functionality without writing custom query._

## 4. Cover Service class with Unit test.

Service class is suggested to have one public method to fetch all data, needed for dashboard. This method
should be covered with Unit test. Unit test means that all external calls from the service are replaced by mocks.
And service class is only one real object in the test, created via “new” operator.

## 5. Add multi-lingual support of user interface.

Translate user interface into 2 languages: Russian and English.
Locale should be defined by part of requested URL. For example, /en/calendar – is English dashboard,
/ru/calendar – is Russian one.

**Tip:** _Do not translate data, only interface. So, “press of a bar” – will be the same in both locales,
but “today” would change._

## 6. Add authentication.

Add authentication via form. Users should be stored in database. Use “plaintext” password encoder to simplify testing.
No need to create registration form, just generate users via fixtures. Although, login/logout links in template
are needed.

Also Exercise entity should have relation to User entity, so when somebody is logged in – he sees only his own
exercises.

## 8. Static Analysis Tools.

Update your composer.json require-dev section to install these tools:

* [PHP_CodeSniffer][phpcs] (Use [PSR2][psr2] coding style guide rules set)
* [PHP Mess Detector][phpmd]
* [PHP Copy/Paste Detector][phpcpd]

Check your "src/" folder and try to clean all errors/warnings.  

## 7. Share your code.

Commit your code into [GitHub][github] and send the link as a result of fulfilled home task.

[calendar_table]:       {{ site.baseurl }}/assets/calendar_table.png
[github]:               https://github.com/
[alice]:                https://github.com/hautelook/AliceBundle
[phpcs]:                https://github.com/squizlabs/PHP_CodeSniffer
[phpmd]:                http://phpmd.org/
[phpcpd]:               https://github.com/sebastianbergmann/phpcpd
[psr2]:                 https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md