---
layout: shop
title: Shop
label: a-z
---
{% assign products = site.products | sort "label" %}
{% for product in products %}
* [{{ product.label }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}
{% endfor %}
