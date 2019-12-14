---
title: 物理
layout: page
---

{% assign topics = site.science %}

{% for post in topics %}
{% if post.categories contains '物理' %}


<div class="card shadow shadow-lg--hover mt-5">
  <div class="card-body">
    <div class="d-flex px-3">
      <div>
        <div class="icon icon-shape bg-warning rounded-circle text-white">
          <i class="ni ni-bulb-61"></i>
        </div>
      </div>
      <div class="pl-4">
        <h5 class="title text-warning">{{ post.title }}</h5>
        <p></p>
        <a href="{{ post.url | prepend: site.baseurl }}" class="text-warning">查看</a>
      </div>
    </div>
  </div>
</div>



{% endif %}
{% endfor %}