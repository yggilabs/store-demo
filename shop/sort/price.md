---
layout: shop
---
[Home]({{ site.github.url }}) > [Shop]({{ site.github.url }}/shop) > [Sort: price]({{ site.github.url }}/shop/sort/price)

{% assign products = products | sort "stock.price.value" | reverse %}
