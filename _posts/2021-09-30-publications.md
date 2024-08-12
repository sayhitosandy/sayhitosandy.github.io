---
layout: post
---

{% for publication in site.data.publications limit:1 %}
<div style="margin-bottom: 20px;">
    <div style="display: flex; align-items: flex-start; margin-top: 10px;">
        <div style="flex: 0 0 30px; text-align: right; padding-right: 5px;">{{ forloop.index }}.</div>
        <div style="flex: 3; padding-left: 5px; text-align: justify;">
            {{ publication.author }} {{ publication.year }}. <strong>{{ publication.title }}</strong> 
            {{ publication.description }}
            <br>
        </div>
    </div>
    <div style="margin-top: 10px; margin-left: 30px; text-align: justify;">
        {% if publication.image %}
            <div style="text-align: center; margin-left: 20px; margin-bottom: 20px; margin-top: 20px">
                <img src="{{ publication.image }}" alt="{{ publication.title }}" style="width: 75%"/>
            </div>
        {% endif %}
        {{ publication.abstract | markdownify }}
        <br>
    </div>
</div>
{% endfor %}

<!-- more -->

{% for publication in site.data.publications offset:1 %}
<div style="margin-bottom: 20px;">
    <div style="display: flex; align-items: flex-start; margin-top: 10px;">
        <div style="flex: 0 0 30px; text-align: right; padding-right: 5px;">{{ forloop.index | plus:1 }}.</div>
        <div style="flex: 3; padding-left: 5px; text-align: justify;">
            {{ publication.author }} {{ publication.year }}. <strong>{{ publication.title }}</strong> 
            {{ publication.description }}
        </div>
    </div>
    <div style="margin-top: 10px; margin-left: 30px; text-align: justify;">
        {% if publication.image %}
            <div style="text-align: center; margin-left: 20px; margin-bottom: 20px; margin-top: 20px">
                <img src="{{ publication.image }}" alt="{{ publication.title }}" style="width: 75%"/>
            </div>
        {% endif %}
        {{ publication.abstract | markdownify }}
        <br>
        <br>
    </div>
</div>
{% endfor %}
