---
layout: content
title: Shop
---
[Home]({{ site.github.url }}) > [Shop]({{ site.github.url }}/shop)

Sort: [Price]({{ site.github.url }}/shop/sort/price)

{% for product in site.products %}
* [{{ product.label }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}
{% endfor %}
