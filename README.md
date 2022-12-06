# 时光与树
<!-- .slide -->
{% if page.jekyll-theme-WuK.tags.vega_lite.enable %}

```vega-lite
{% capture json_data %}[
{% for tag in site.tags reversed %}
 , {"tags": "{{ tag[0] }}", "count": {{ tag[1].size }} }
{% endfor %}
]{% endcapture %}
{% assign json_data = json_data | remove_first: "," %}
{
  "data": { "values": {{ json_data }} },
  "encoding": {
    "y": {"field": "tags", "type": "nominal"},
    "x": {"field": "count", "type": "quantitative" }
  },
  "mark": "bar"
}
```

{% endif %}
