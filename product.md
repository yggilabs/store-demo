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
{{ page.product.variations | group_by_expression: "attributes","attributes.color" | jsonify }}
```
```javascript
{{ page.product.variations | group_by: "color" | group_by_expression: "item","item.size" | jsonify }}
```