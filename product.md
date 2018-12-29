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
listColor: {{ page.product.variations | map: "attributes" | map: "color" | uniq }}
listSize: {{ page.product.variations | map: "attributes" | map: "size" | uniq }}
<amp-state id="product">
  <script type="application/json">
    {
      price: {{ page.product.price }},
      selectedColor: {{ page.product.variations.first.attributes.color }},      
      selectedSize: {{ page.product.variations.first.attributes.size }},      
    {%- assign mmmm = page.product.variations | group_by: "attributes.color" -%}
    {%- for aaa in mmmm -%}
      "{{ aaa.name }}": 
        {
        {%- assign nnn = aaa.items | group_by: "attributes.size"  -%}
        {%- for bbb in nnn -%}
          "{{ bbb.name }}": 
            {{ bbb.items.first | jsonify }}{% unless forloop.last %},{% endunless %}
        {% endfor %}
        }{% unless forloop.last %},{% endunless %}
    {%- endfor -%}
    }    
  </script>
</amp-state>
<amp-selector name="color"
  layout="container"
  [selected]="product.selectedColor">
  {% assign colors = page.product.variations | map: "attributes" | map: "color" | uniq %}
  <ul>
  {% for color in colors %}
    <li{% if forloop.first %} selected{% endif %} option="{{color}}">{{color}}</li>
  {% endfor %}
  </ul>
</amp-selector>
