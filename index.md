---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
# [13/02/2018 \[math\] |G| = |H||G:H| ](math/lagrange_group.html)
# [11/02/2018 \[math\] cosets are disjoint](math/cosets_are_disjoint.html)


layout: default
---

[NIPS 2017: main ideas & trends](overviews/28122017-nips2017-overview.html)

<h2>Public Activity</h2>
<ul class="posts">
    {% for post in site.categories.public %}
        <li><span>{{ post.date | date_to_string }}</span> » <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

<h2>math</h2>
<ul class="posts">
    {% for post in site.categories.math %}
        <li><span>{{ post.date | date_to_string }}</span> » <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
<!--h2>startups</h2>
<ul class="posts">
    {% for post in site.categories.startups %}
        <li><span>{{ post.date | date_to_string }}</span> » <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></li>
    {% endfor %}
</ul-->
