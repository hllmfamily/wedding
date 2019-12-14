---
title: 更新日志
layout: page
---

{% assign updates = site.updates | sort: "order" %}

{% for post in updates %}

{% if post.exclude != true %}

<div class="card shadow shadow-lg--hover mt-5">
              <div class="card-body">
                <div class="d-flex px-3">
                  <div>
                    <div class="icon icon-shape bg-gradient-info rounded-circle text-white">
                      <i class="ni ni-chat-round"></i>
                    </div>
                  </div>
                  <div class="pl-4">
                    <h5 class="title text-info">{{ post.title }}</h5>
                    <p>{{ post.summary }}</p>
                    <p>{{ post.date | date: "%Y-%m-%d" }}</p>
                    <a href="{{ post.url | prepend: site.baseurl }}" class="text-info">阅读全文</a>
                  </div>
                </div>
              </div>
            </div>
{% endif %}
  
{% endfor %}