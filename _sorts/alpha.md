---
layout: shop
title: Shop
label: a-z
---

{% assign products = site.products | sort "name" %}
{% for product in products %}
* [{{ product.name }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}
{% endfor %}
