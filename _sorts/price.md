---
layout: shop
title: Shop
label: price
---

## sort: price

{% assign products = site.products | sort "stock.price.value" | reverse %}
{% for product in products %}
* [{{ product.label }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}
{% endfor %}
