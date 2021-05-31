## Titanic Dataset

{{ site.data.titanic.csv | inspect }}

| Survived | Pclass | Name | Sex | Age | Siblings/Spouses Aboard | Parents/Children Aboard | Fare |

| 0 |	3 |	Mr. Owen Harris Braund |	male	| 22 | 1	| 0	| 7.25 | 



<table>
  {% for row in site.data.titanic.csv %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>
