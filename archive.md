---
layout: page
title: Archive
---

<!-- simple archive without month/year headings
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> <small>[{{ post.date | date: "%B %d, %Y" }}]</small>
    </li>
  {% endfor %}
</ul-->


<div>
{% for post in site.posts %}
  {% capture currentyear %}{{post.date | date: "%B %Y"}}{% endcapture %}
  {% if currentyear != year %}
    {% unless forloop.first %}</ul>{% endunless %}
    <p>{{ currentyear }}</p>
    <ul>
    {% capture year %}{{currentyear}}{% endcapture %} 
  {% endif %}
    <li>
    	<a href="{{ post.url }}">{{ post.title }}</a> <small>[{{ post.date | date: "%B %d, %Y" }}]</small>
    </li>
    {% if forloop.last %}</ul>{% endif %}
{% endfor %}
</div>

<!--hr />

<*By category:*

<ul>
{% for category in site.categories %}
  <li>{{ category | first }}    
  	<ul>
    {% for posts in category %}
      {% for post in posts %}
        <li><a href="{{ post.url }}">{{ post.title }}</a> <small>[{{ post.date | date: "%B %d, %Y" }}]</small></li>
      {% endfor %}
    {% endfor %}
    </ul>
  </li>
{% endfor %}
</ul-->


