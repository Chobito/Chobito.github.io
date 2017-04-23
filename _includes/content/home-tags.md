---
layout: page
title: Tags
---

  <div class="tags-full-list">
	{% for tag in site.tags %}
		<a href="/menu/tagurls#{{ tag[0] | slugify }}"/
		 class="simple-tag" style="font-size: {{ tag | last | size  |  times: 3 | plus: 80  }}%">
			<i class="fa fa-tag" aria-hidden="true">

			{{ tag[0] | replace:'-', ' ' }} ({{ tag | last | size }})
			</i>
		</a>
	{% endfor %}
  </div>


  <div class="tags-postlist">
    {% for tag in site.tags %}
    <h2 id="{{ tag[0] | slugify }}">{{ tag[0] }}</h2>
    
    <ul>
      {% for post in tag[1] %}
        <a class="tag-post" href="{{ site.baseurl }}{{ post.url }}">
		  <li>
			{{ post.title }}
		  <small class="post-date">{{ post.date | date_to_string }}</small>
		  </li>
        </a>
      {% endfor %}
    </ul>
    
    {% endfor %}
  </div>
</div>
