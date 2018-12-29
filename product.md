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
{{ page.product.variations | jsonify }}
```
```javascript
{ 
{% assign m = page.product.variations | group_by: "attributes.color" %}
{% for a in m %}
  "{{ a.name }}": 
    {
    {% assign n = a.items | group_by: "attributes.size"  %}
    {% for b in n %}
      "{{ b.name }}": 
        {
          {{ b.items.first }}
        }
    {% endfor %}
    },
{% endfor %}
}
```
```javascript
{{ page.product.variations | group_by: "attributes.color" | group_by: "items.attributes.size" | jsonify }}
```
