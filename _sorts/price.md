---
layout: content
title: Shop
---
[Home]({{ site.github.url }}) > [Shop]({{ site.github.url }}/{{ page.collection }}) > [Sort: price]({{ site.github.url }}{{ page.url }})

Sort: {% for sort in site.sorts %}
[{{sort.name}}]({{ site.github.url }}{{ sort.url }}) 
{% endfor %}

{% assign products = site.products | sort "stock.price.value" | reverse %}
{% for product in products %}
* [{{ product.label }}]({{ site.github.baseurl }}{{ product.url }})

  {{ product.stock.price.value }} {{ product.stock.price.currency }}
{% endfor %}
