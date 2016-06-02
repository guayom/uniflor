---
title: Products
layout: products
---
<table class="table table-bordered">
    <tr>
      <th></th>
      <th></th>
      {% for company in site.data.productos.empresas %}
        <th>
          {{company[1] | capitalize}}
        </th>
      {% endfor %}
    </tr>
    {% for p in site.data.productos.products %}
    <tr>
      <td>
        {{p[0] | capitalize}}
      </td>
     </tr>
    {% endfor %}
</table>
