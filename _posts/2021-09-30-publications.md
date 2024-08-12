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
        {% if publication.image %}
            <div style="flex: 3; padding-top: 5px; padding-left: 30px">
                <img src="{{ publication.image }}" alt="{{ publication.title }}" style="width: 100%; max-width: 300px;"/>
            </div>
        {% endif %}
    </div>
    <div style="display: flex; align-items: flex-start; margin-top: 5px; padding-left: 35px">
        {{ publication.abstract | markdownify }}
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
            <br>
        </div>
        {% if publication.image %}
            <div style="flex: 3; padding-top: 5px; padding-left: 30px">
                <img src="{{ publication.image }}" alt="{{ publication.title }}" style="width: 100%; max-width: 300px;"/>
            </div>
        {% endif %}
    </div>
    <div style="display: flex; align-items: flex-start; margin-top: 5px; padding-left: 35px">
        {{ publication.abstract | markdownify }}
    </div>
</div>
{% endfor %}
