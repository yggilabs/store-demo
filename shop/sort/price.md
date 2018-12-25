---
layout: content
title: Products
---
[Home]({{ site.github.url }}) > [Products]({{ site.github.url }}/shop) > [Sort: price]({{ site.github.url }}/shop/sort/price)
## Products
{% assign products = site.products | sort "stock.price.value" | reverse %}
{% for product in products %}
* [{{ product.label }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}
{% endfor %}
