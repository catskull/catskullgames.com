---
layout: default
description: New games for old consoles including Nintendo Gameboy and more!
---

<div class="tiles">
  {%  assign sorted_posts = site.posts | sort: 'pos' %}
  {% for post in sorted_posts %}
    {% unless post.hidden %}
      {% if post.featured %}
      <div class="tile" id="featured">
      {% else %}
      <div class="tile">
      {% endif %}
      	<a href="{{ post.url }}">
      		<img src="{{ post.image }}" alt="{{ post.description }}"/>
      		<p>{{ post.title }}</p>
    	  	{% if post.new %}
    	  		<div class="after">
        			<p>New!</p>
        		</div>
        	{% endif %}
      		<div class="price">
      		  <p>${{ post.price }}.00</p>
      		</div>
      	</a>
    	</div>
    {% endunless %}
  {% endfor %}
</div>
