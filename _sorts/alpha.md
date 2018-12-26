---
layout: shop
title: Shop
label: a-z
---
{% assign products = site.products | sort "label" %}

* [{{ product.label }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}

