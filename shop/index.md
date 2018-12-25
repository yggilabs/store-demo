---
layout: content
title: Products
---
[Home]() > [Shop](shop)

Sort: [Price](shop/sort/price)

## Products
{% for product in site.products %}
* [{{ product.label }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}
{% endfor %}
