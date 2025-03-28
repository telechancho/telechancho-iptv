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
      <td nowrap>
        <img alt='Logo de {{ channel.name }}' width='96' src='{{ site.url }}{{ site.baseurl }}/{% if channel.channel-type %}{{ channel.channel-type }}{% else %}tv{% endif %}logos/{{ channel.logo }}'/>
      </td>
      <td>
        <b>{{ channel.name }}</b>
        <br>
        <br>
        <b>Posee guía de programación:</b> {% if channel.tvg-id %}Sí{% else %}No{% endif %}
        <br>
        <br>
        <b>Utiliza un User Agent específico:</b> {% if channel.user-agent %}Sí, utiliza un User Agent {% if channel.user-agent contains 'Edg/' %}de <b>Microsoft Edge</b> {% elsif channel.user-agent contains 'EdgA/' %}de <b>Microsoft Edge</b> {% elsif channel.user-agent contains 'EdgiOS/' %}de <b>Microsoft Edge</b> {% elsif channel.user-agent contains 'Chrome/' %}de <b>Chrome</b> {% elsif channel.user-agent contains 'CriOS/' %}de <b>Chrome</b> {% elsif channel.user-agent contains 'FxiOS/' %}de <b>Firefox</b> {% elsif channel.user-agent contains 'Safari/' %}de <b>Safari</b> {% elsif channel.user-agent contains 'Firefox/' %}de <b>Firefox</b> {% elsif channel.user-agent contains 'Edge/' %}de <b>Microsoft Edge (Legacy)</b> {% elsif channel.user-agent contains 'MSIE' %}de <b>Internet Explorer</b> {% else %} {% endif %}{% if channel.user-agent contains 'Android' %}corriendo en <b>Android</b>{% elsif channel.user-agent contains 'iPhone' %}corriendo en <b>iOS</b>{% elsif channel.user-agent contains 'iPad' %}corriendo en <b>iPadOS</b>{% elsif channel.user-agent contains 'iPod' %}corriendo en <b>iOS</b>{% elsif channel.user-agent contains 'Windows' %}corriendo en <b>Windows</b>{% elsif channel.user-agent contains 'Macintosh' %}corriendo en <b>macOS</b>{% elsif channel.user-agent contains 'Mac OS X' %}corriendo en <b>macOS</b>{% elsif channel.user-agent contains 'CrOS' %}corriendo en <b>Chrome OS</b>{% elsif channel.user-agent contains 'Linux' %}corriendo en <b>Linux</b>{% elsif channel.user-agent contains 'X11' %}corriendo en <b>Unix</b>{% else %} {% endif %}{% else %}No, no utiliza un User Agent específico {% endif %}
        <br>
        <b>Utiliza un Referer específico:</b> {% if channel.referer %}Sí{% else %}No{% endif %}
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>
{% endfor %}
