---
title: Canales disponibles en Telechancho Infinity
permalink: /canales
---
# Canales disponibles en Telechancho Infinity 
Aqui podras ver la lista de todos los canales disponibles en Telechancho Infinity

{% for channelgroup_hash in site.data.channels %}{% assign channelgroup = channelgroup_hash[1] %}
## {{ channelgroup.group-title }}
<table>
  <thead>
    <tr><th align="left">Logo del canal</th><th align="left">Nombre y características del canal</th></tr>
  </thead>
  <tbody>
    {% for channel in channelgroup.channels %}
    <tr>
      <td>
        <img alt='Logo de {{ channel.name }}' width='70' src='{{ site.url }}{{ site.baseurl }}/{% if channel.channel-type %}{{ channel.channel-type }}{% else %}tv{% endif %}logos/{{ channel.logo }}'/>
      </td>
      <td>
        <b>{{ channel.name }}</b>
        <br>
        <br>
        <b>Posee guía de programación:</b> {% if channel.tvg-id %}Sí{% else %}No{% endif %}
        <br>
        <br>
        <b>Utiliza un User Agent específico:</b> {% if channel.user-agent %}Sí{% else %}No{% endif %}
        <br>
        <b>Utiliza un Referer específico:</b> {% if channel.referer %}Sí{% else %}No{% endif %}
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>
{% endfor %}
