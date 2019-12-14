---
title: 科学集市
layout: page
---

我们在婚礼的当天下午准备了一个科学集市，我们准备了一些实验仪器，现场向小朋友们宣传科学。当天的科学集市很成功。


当然，我们一开始也准备过一点科学知识，但是最后没有用上，就当作遗迹记录在这里了。

也可以[点击这里随机查看一条](random)。


{% assign topics = site.science %}

{% assign rawtags = "" %}
{% for post in site.science %}
{% assign scategories = post.categories | join:'|' | append:'|' %}
{% assign rawcategories = rawcategories | append:scategories %}
{% endfor %}

{% assign rawcategories = rawcategories | split:'|' | sort %}



{% assign categories = "" %}

{% for category in rawcategories %}
{% if category != "" %}

{% if categories == "" %}
{% assign categories = category | split:'|' %}
{% endif %}

{% unless categories contains category %}
{% assign categories = categories | join:'|' | append:'|' | append:category | split:'|' %}
{% endunless %}
{% endif %}
{% endfor %}



{% for category in categories %}

{% assign catcount = 0 %}

    {% for post in site.science %}
        {% if post.categories contains category %}

            {% assign catcount = catcount | plus: 1 %}

{% capture url_base %} {{ post.path | replace:'_science','' | replace:'/', ' ' | truncatewords: 1  | replace:' ','' | remove:'...' }} {% endcapture %}



        {% endif %}
    {% endfor %}

  <div class="card shadow shadow-lg--hover mt-5">
  <div class="card-body">
    <div class="d-flex px-3">
      <div>
        <div class="icon icon-shape bg-warning rounded-circle text-white">
          <i class="ni ni-bulb-61"></i>
        </div>
      </div>
      <div class="pl-4">
        <h5 class="title text-warning">{{ category }}</h5>
        <p>共有 {{ catcount }} 条知识</p>
        <a href="{{ site.baseurl }}/science/{{ url_base | slugify }}" class="text-warning">查看</a>
      </div>
    </div>
  </div>
</div>


{% endfor %}
