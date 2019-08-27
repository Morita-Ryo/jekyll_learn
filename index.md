---
layout : default
title: test page
---

# Test

Test
Test

Test
Test

{% for team_member in site.team_members %}

  {% capture path %}
  {% include getpath.md page=team_member %}
  {% endcapture %}

  {% assign img = path | strip | append: "img/" | append: team_member.img %}

  {% comment %}
  {% assign ext = team_member.url | remove: team_member.id %}
  {% assign img = team_member.url |
     remove: ext | remove: team_member.slug |
    append: "img/" | append: team_member.img %}
  {% endcomment %}

  <h2>
  <img src="{{ img }}"><br>{{ team_member.name }}<br>{{ team_member.position }}
  </h2>
  <p>{{ team_member.content | markdownify }}</p>
  <pre>
{{ team_member | inspect}}
</pre>
{% endfor %}
