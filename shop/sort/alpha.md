---
layout: shop
---
[Home]({{ site.github.url }}) > [Shop]({{ site.github.url }}/shop) > [Sort: a-z]({{ site.github.url }}/shop/sort/alpha)

{% assign products = site.shop.products | sort "stock.label" | reverse %}
