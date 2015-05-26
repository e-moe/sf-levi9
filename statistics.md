---
layout: page
title: Statistics
permalink: /statistics/
---
* TOC
{:toc}

## Training Statistics.

{% assign statistics = (site.data.statistics | sort: 'score') %}

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Tasks submitted</th>
            <th>▼ Score</th>
        </tr>
    </thead>
    <tbody>
        {% for row in statistics reversed %}
        <tr>
            <td>{{ row.name }}</td>
            <td>{{ row.tasks }}</td>
            <td>{{ row.score }}</td>
        </tr>
        {% endfor %}
    </tbody>
</table>