---
layout: default
title: Episode Archive
permalink: /episodes/
---

{% raw %}
<header style="text-align: center; margin-top: 2em;">
  <img src="{{ '/assets/images/FNV-logo-tweaked.jpg' | relative_url }}" alt="Friday Night Videos Logo"
       style="max-width: 300px; margin-bottom: 1em;">
  <h1>Friday Night Videos Episode Guide</h1>
</header>

<table>
  <thead>
    <tr>
      <th>Air Date</th>
      <th>Private Reel / Guest Host</th>
      <th>Notes</th>
      <th>Recording</th>
    </tr>
  </thead>
  <tbody>
    {% assign sorted_episodes = site.episodes | sort: "date" %}
    {% for episode in sorted_episodes %}
      <tr>
        <td><a href="{{ episode.url | relative_url }}">{{ episode.title }}</a></td>
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
          {% if episode.index_notes %}
            {{ episode.index_notes }}
          {% else %}
            —
          {% endif %}
        </td>
        <td>
          {% case episode.recording_status %}
            {% when "complete" %}
              <span style="color:#00cc66;font-weight:bold;">✔️ Complete</span>
            {% when "incomplete" %}
              <span style="color:#ffaa00;font-weight:bold;">⏳ Incomplete</span>
            {% when "none" %}
              <span style="color:#cc0033;font-weight:bold;">❌ None</span>
            {% else %}
              —
          {% endcase %}
        </td>
      </tr>
    {% endfor %}
  </tbody>
</table>
{% endraw %}