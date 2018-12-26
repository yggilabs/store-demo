---
layout: content
title: Shop
---
[Home]({{ site.github.url }}) > [Shop]({{ site.github.url }}/shop)
{% assign products = site.products | sort "label" | reverse %}
{% for product in products %}
* [{{ product.label }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}
{% endfor %}
