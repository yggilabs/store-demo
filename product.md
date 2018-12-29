---
layout: content
product:
  id: prod_123456789
  name: t-shirt
  price: 1500
  attributes:
    - color
    - size
  variations:
    - attributes:
        color: black
        size: S
    - attributes:
        color: black
        size: M
    - attributes:
        color: black
        size: L
    - attributes:
        color: gray
        size: S
    - attributes:
        color: gray
        size: M
    - attributes:
        color: gray
        size: L    
---
```javascript
{
{% assign mmmm = page.product.variations | group_by: "attributes.color" %}
{% for aaa in mmmm %}
  "{{ aaa.name }}": 
    {
    {% assign nnn = aaa.items | group_by: "attributes.size"  %}
    {% for bbb in nnn %}
      "{{ bbb.name }}": 
        {{ bbb.items.first | jsonify }}{% unless forloop.last %},{% endunless %}
    {% endfor %}
    }{% unless forloop.last %},{% endunless %}
{% endfor %}
}
```
