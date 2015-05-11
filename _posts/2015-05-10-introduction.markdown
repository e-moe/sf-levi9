---
layout: post
title:  "Training organisation and schedule"
date:   2015-05-10 09:00:00
category: training
tags:
    - training
    - schedule
excerpt: |
    Training organisation.
    Training consist of 4 workshops (each with it's own home task) and one optional warmup assignment to check
    trainees Symfony framework knowledge level.
---
* TOC
{:toc}

## Training organisation.

Training consist of 4 workshops (each with it's own home task) and one optional [warmup][warmup] assignment to check
trainees Symfony framework knowledge level.

## Schedule.

<table>
    <thead>
        <tr>
            <th>Date</th>
            <th>Event</th>
        </tr>
    </thead>
    <tbody>
        {% for event in site.data.schedule %}
        <tr>
            <td>{{ event.date | date_to_string }}</td>
            <td>{{ event.name }}</td>
        </tr>
        {% endfor %}
    </tbody>
</table>

[warmup]:       {{ site.baseurl }}{% post_url 2015-05-12-warmup %}