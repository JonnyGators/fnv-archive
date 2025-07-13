---
layout: default
title: Episode Archive
permalink: /episodes/
---

<h1>Friday Night Videos Archive</h1>

<table>
  <thead>
    <tr>
      <th>Air Date</th>
      <th>Private Reel / Guest Host</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    {% assign sorted_episodes = site.episodes | sort: "title" %}
    {% for episode in sorted_episodes %}
      <tr>
        <td><a href="{{ episode.url }}">{{ episode.title }}</a></td>
        <td>
          {% if episode.private_reel %}
            {{ episode.private_reel }}
          {% elsif episode.guest_host %}
            {{ episode.guest_host }}
          {% else %}
            —
          {% endif %}
        </td>
        <td>
          {% if episode.notes %}
            {{ episode.notes }}
          {% else %}
            —
          {% endif %}
        </td>
      </tr>
    {% endfor %}
  </tbody>
</table>