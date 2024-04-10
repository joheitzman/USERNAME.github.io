---
layout: post
title: Table Test
date: '2024-04-10'
categories: Data
tags:[raw_data]
---
###There should be a table below



<script><table>
  {% for row in Name.Date.Thing.Comment %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table></script>