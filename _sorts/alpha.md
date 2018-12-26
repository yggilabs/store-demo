---
layout: content
title: Shop
label: a-z
---

[Home]({{ site.github.url }}) > [Shop]({{ site.github.url }}/{{ page.collection }})

Sort: {% for sort in site.sorts %}
  * [{{ sort.label }}]({{ site.github.url }}{{ sort.url }}){{ seperator }}
{% endfor %}


{% assign products = site.products | sort "label" | reverse %}
{% for product in products %}
* [{{ product.label }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}
{% endfor %}
