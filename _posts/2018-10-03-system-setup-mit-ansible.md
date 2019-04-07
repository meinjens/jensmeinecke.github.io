---
layout: post
title: System-Setup mit Ansible
tags: [raspberrypi, pondpi, ansible]
comments: true
---

		
<p>Das Setup der Raspberry Pis habe ich nun schon mehrfach durchführen müssen. In meinem letzten Job habe ich ein schönes Tool gefunden, womit ich das Setup reproduzierbar in Code gießen kann: Ansible.</p>

<p><a href="https://www.ansible.com/" target="_blank" rel="noopener">Ansible</a>&nbsp;ist ein Automatisierungs Tool für IT Infrastrukturen. Mit Hilfe des Tools richte ich das Betriebssystem der beiden Raspberry Pis ein.</p>

<div class="wp-block-image"><figure class="aligncenter"><img src="http://meinjens.de/wp-content/uploads/2018/09/ansible-setup.png" alt="" class="wp-image-206" srcset="http://meinjens.de/wp-content/uploads/2018/09/ansible-setup.png 354w, http://meinjens.de/wp-content/uploads/2018/09/ansible-setup-300x170.png 300w" sizes="(max-width: 354px) 100vw, 354px"><figcaption>Setup der Raspberry Pis mit Ansible</figcaption></figure></div>

<p>Ansible ist in Python implementiert. Deswegen ist Windows als Kontrollmaschine nicht gut geeignet. Auf <a href="https://docs.microsoft.com/en-us/windows/wsl/install-win10" target="_blank">Windows 10 lässt sich jedoch Linux als Subsystem</a> nutzen.</p>


<p>Das Ansible Projekt liegt im Ordner <a href="https://github.com/meinjens/pondpi/tree/master/setup" target="_blank" rel="noopener"><em>setup</em></a>&nbsp;<br>Hier ein kurzer Überblick über das Projekt-Layout des Moduls:</p>

<pre class="wp-block-code">
<div class="codecolorer-container text twitlight" style="overflow:auto;white-space:nowrap;width:100%;"><div class="text codecolorer">setup<br>
&nbsp; +-- callback_plugins/ &nbsp; &nbsp; &nbsp; &nbsp;(Plugin-Verzeichnis)<br>
&nbsp; +-- group_vars/ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(Variablen für Server-Gruppen)<br>
&nbsp; +-- host_vars/ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (Variablen für einzelne Server)<br>
&nbsp; +-- roles/ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (Verzeichnis für die Ansible Rollen)<br>
&nbsp; | &nbsp; ansible.cfg &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;(Ansible Einstellungen für das Projekt)<br>
&nbsp; | &nbsp; setup_base.yml &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (Playbook für das Basis Setup aller Pis)<br>
&nbsp; | &nbsp; setup_controlstation.yml (Playbook zum Setup der Kontrolstation)<br>
&nbsp; | &nbsp; setup_researchship.yml &nbsp; (Playbook zum Setup des Bootes)</div></div>

</pre>

<p>Mit verschiedenen Rollen werden die Dienste auf den Raspberry Pis installiert und konfiguriert, wie z.B. einen DHCP-Server. Folgende Rollen nutzen wir für die Installation der beiden Pis:</p>

<h2>Base Rolle</h2>

<p>Die Base Rolle führt Basiseinstellungen auf den Raspberry Pis durch, wie z.B. Updates, Hardware Setup.</p>

<pre class="wp-block-code">
<div class="codecolorer-container text twitlight" style="overflow:auto;white-space:nowrap;width:100%;"><div class="text codecolorer">ansible-playbook setup_base.yml</div></div>

</pre>

<h2>Accesspoint Rolle</h2>

<p>Diese Rolle installiert alle Dienste, die zum Betrieb des Pis als Accesspoint notwendig sind. Für die WLAN Verbindungen nutzen wir den Dienst <a href="https://packages.debian.org/de/stretch/hostapd" target="_blank" rel="noopener">HostAPD</a>. Für den DHCP-Server nutzen wir <a href="https://packages.debian.org/stretch/dnsmasq" target="_blank" rel="noopener">DNSmasq</a>.</p>

<p>Zur Installation oder Wartung wird lediglich das entsprechende Playbook ausgeführt. Beispiel:</p>



<pre class="wp-block-code">
<div class="codecolorer-container text twitlight" style="overflow:auto;white-space:nowrap;width:100%;"><div class="text codecolorer">ansible-playbook setup_controlstation.yml</div></div>

</pre>



<h2>Weitere Schritte</h2>



<p>Die nächsten Rollen, die ich implementiere, installieren die Test-Tools, nginx, Flask Server usw. Die Rollen findet ihr ebenfalls im <a href="https://github.com/meinjens/pondpi/tree/master/setup" target="_blank">Github-Repository vom PondPi</a>.</p>
