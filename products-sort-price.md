---
layout: content
title: Products
---
[Home](/) > [Products](/products) > [Sort: price](/products-sort-price)
## Products
{% assign products = site.products | sort "stock.price.value" %}
{% for product in products %}
* [{{ product.label }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}
{% endfor %}
