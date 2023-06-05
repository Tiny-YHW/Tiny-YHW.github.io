---
layout: page
title: About
description: description
keywords: Tiny-Y
comments: true
menu: 关于
permalink: /about/
---

我是Tiny-Y

专业PCB Layout设计工程师

个人擅长钻研与PCB设计相关的，软件、标准化、效率、技巧、二次开发等

## 联系

<ul>
{% for website in site.data.social %}
<li>{{website.sitename }}：<a href="{{ website.url }}" target="_blank">@{{ website.name }}</a></li>
{% endfor %}

<li>
微信公众号：<br />
<img style="height:192px;width:192px;border:1px solid lightgrey;" src="{{ site.url }}/assets/images/qrcode.jpg" alt="Layouto" />
</li>
<li>
QQ群：[318558588](https://jq.qq.com/?_wv=1027&k=JHFtV92M){:target="_blank"}
</li>
</ul>


## Skill Keywords

{% for skill in site.data.skills %}
### {{ skill.name }}
<div class="btn-inline">
{% for keyword in skill.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
