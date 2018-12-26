---
layout: content
title: Shop
---
[Home]({{ site.github.url }}) > [Shop]({{ site.github.url }}/shop) > [Sort: price]({{ site.github.url }}/shop/sort/price)

Sort: [Price]({{ site.github.url }}/shop/sort/price), [A-Z]({{ site.github.url }}/shop/sort/alpha)
{% for product in site.products %}
* [{{ product.label }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}
{% endfor %}
