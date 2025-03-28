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
        <b>Utiliza un User Agent específico:</b> {% if channel.user-agent %}Sí, utiliza un User Agent {% if channel.useragent contains 'Edg/' %}de <b>Microsoft Edge</b> {% elsif channel.useragent contains 'EdgA/' %}de <b>Microsoft Edge</b> {% elsif channel.useragent contains 'EdgiOS/' %}de <b>Microsoft Edge</b> {% elsif channel.useragent contains 'Chrome/' %}de <b>Google Chrome</b> {% elsif channel.useragent contains 'CriOS/' %}de <b>Google Chrome</b> {% elsif channel.useragent contains 'FxiOS/' %}de <b>Mozilla Firefox</b> {% elsif channel.useragent contains 'Safari/' %}de <b>Safari</b> {% elsif channel.useragent contains 'Firefox/' %}de <b>Mozilla Firefox</b> {% elsif channel.useragent contains 'Edge/' %}de <b>Microsoft Edge (Legacy)</b> {% else %} {% endif %}{% if channel.useragent contains 'Android' %}corriendo en <b>Android</b>{% if channel.useragent contains 'iPhone' %}corriendo en <b>iOS</b>{% if channel.useragent contains 'iPad' %}corriendo en <b>iPadOS</b>{% if channel.useragent contains 'iPod' %}corriendo en <b>iOS</b>{% if channel.useragent contains 'Windows' %}corriendo en <b>Windows</b>{% if channel.useragent contains 'Macintosb' %}corriendo en <b>macOS</b>{% if channel.useragent contains 'Mac OS X' %}corriendo en <b>macOS</b>{% if channel.useragent contains 'CrOS' %}corriendo en <b>Chrome OS</b>{% if channel.useragent contains 'Linux' %}corriendo en <b>Linux</b>{% if channel.useragent contains 'X11' %}corriendo en <b>Unix</b>{% else %} {% endif %}{% else %}No, no utiliza un User Agent específico {% endif %}
        <br>
        <b>Utiliza un Referer específico:</b> {% if channel.referer %}Sí{% else %}No{% endif %}
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>
{% endfor %}
