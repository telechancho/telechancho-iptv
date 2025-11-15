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
    {% for channel in channelgroup.channels %}{% unless channel.hidden %}
    <tr>
      <td nowrap>
        <img alt='Logo de {{ channel.name }}' width='96' src='{{ site.url }}{{ site.baseurl }}/{% if channel.channel-type %}{{ channel.channel-type }}{% else %}tv{% endif %}logos/{{ channel.logo }}'/>
      </td>
      <td><b style='font-size:25px'>{{ channel.name }}</b>
        <br>
        <br>
        <b>User Agent específico:</b> {% if channel.user-agent %}Utiliza un User Agent {% if channel.user-agent contains 'Edg/' %}de <b>Microsoft Edge</b> {% elsif channel.user-agent contains 'EdgA/' %}de <b>Microsoft Edge</b> {% elsif channel.user-agent contains 'EdgiOS/' %}de <b>Microsoft Edge</b> {% elsif channel.user-agent contains 'Chrome/' %}de <b>Google Chrome</b> {% elsif channel.user-agent contains 'CriOS/' %}de <b>Google Chrome</b> {% elsif channel.user-agent contains 'FxiOS/' %}de <b>Mozilla Firefox</b> {% elsif channel.user-agent contains 'Safari/' %}de <b>Safari</b> {% elsif channel.user-agent contains 'Netscape/' %}de <b>Netscape</b> {% elsif channel.user-agent contains 'Firefox/' %}de <b>Mozilla Firefox</b> {% elsif channel.user-agent contains 'Edge/' %}de <b>Microsoft Edge (Legacy)</b> {% elsif channel.user-agent contains 'MSIE' %}de <b>Internet Explorer</b> {% else %} {% endif %}{% if channel.user-agent contains 'Android' %}corriendo en <b>Android</b>{% elsif channel.user-agent contains 'iPhone' %}corriendo en <b>iOS</b>{% elsif channel.user-agent contains 'iPad' %}corriendo en <b>iPadOS</b>{% elsif channel.user-agent contains 'iPod' %}corriendo en <b>iOS</b>{% elsif channel.user-agent contains 'Windows NT 11.0' %}corriendo en <b>Windows 11</b>{% elsif channel.user-agent contains 'Windows NT 10.0' %}corriendo en <b>Windows 10</b>{% elsif channel.user-agent contains 'Windows NT 6.3' %}corriendo en <b>Windows 8.1</b>{% elsif channel.user-agent contains 'Windows NT 6.2' %}corriendo en <b>Windows 8</b>{% elsif channel.user-agent contains 'Windows NT 6.1' %}corriendo en <b>Windows 7</b>{% elsif channel.user-agent contains 'Windows NT 6.0' %}corriendo en <b>Windows Vista</b>{% elsif channel.user-agent contains 'Windows NT 5.2' %}corriendo en <b>Windows Server 2003</b>{% elsif channel.user-agent contains 'Windows NT 5.1' %}corriendo en <b>Windows XP</b>{% elsif channel.user-agent contains 'Windows NT 5.0' %}corriendo en <b>Windows 2000</b>{% elsif channel.user-agent contains 'Windows NT 4.0' %}corriendo en <b>Windows NT 4.0</b>{% elsif channel.user-agent contains 'Windows NT 3.51' %}corriendo en <b>Windows NT 3.51</b>{% elsif channel.user-agent contains 'Windows' %}corriendo en <b>Windows</b>{% elsif channel.user-agent contains 'Mac OS X' %}corriendo en <b>macOS</b>{% elsif channel.user-agent contains 'PPC Mac OS' %}corriendo en <b>Mac OS Classic (PowerPC)</b>{% elsif channel.user-agent contains 'Macintosh' %}{% if channel.user-agent contains '68k' %}corriendo en <b>Mac OS Classic(Motorola 68000)</b>{% else %}corriendo en <b>Mac OS Classic</b>{% endif %}{% elsif channel.user-agent contains 'CrOS' %}corriendo en <b>Chrome OS</b>{% elsif channel.user-agent contains 'Linux' %}corriendo en <b>Linux</b>{% elsif channel.user-agent contains 'X11' %}corriendo en un sistema <b>Unix-like</b>{% else %} {% endif %}{% else %}No utiliza un User Agent específico {% endif %}
        <br>
        <b>Referer específico:</b> {% if channel.referer %}Sí{% else %}No{% endif %}
      </td>
    </tr>
    {% endunless %}{% endfor %}
  </tbody>
</table>
{% endfor %}
