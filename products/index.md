---
title: Products
layout: products
header_class: largest no-margin-bottom
identifier: products
weight: 15
---

  <table class="table table-bordered table-striped table-matriz table-fixed">
    <thead>
      <tr>
        <th colspan="2" class="text-center">Product Category</th>
        {% for company in site.data.productos.empresas %}
          <th width="10%" class="text-center">
            {{company[1]}}
          </th>
        {% endfor %}
      </tr>
    </thead>
    <div class="scrollable-area">
      <tbody>
        {% for p in site.data.productos.products %}

          {% for p1 in p[1] %}
          <tr>
            {% if forloop.first == true %}
              <td rowspan="{{ forloop.length }}" class="{{p[0]}}">
                {{p[0] | capitalize}}
              </td>
            {% endif %}
            <td class="{{p[0]}} filterable-cell">{{ p1.name | capitalize_all }}</td>
            {% for company in site.data.productos.empresas %}
              <td class="text-center bullet">
                {% if p1.companies contains company[0] %}&#8226;{% endif %}
              </td>
            {% endfor %}
          </tr>
          {% endfor %}
        {% endfor %}
      </tbody>
    </div>
  </table>

<script src="{{base}}/js/jquery.stickytableheaders.min.js"></script>
<script type="text/javascript">
$(window).scroll(function() {
  if ($(document).scrollTop() >= 300) {
    $('.table').stickyTableHeaders({
      fixedOffset: $('#main-navbar-container')
    });
  } else {
    $('.table').stickyTableHeaders('destroy');    
  }
});
</script>
