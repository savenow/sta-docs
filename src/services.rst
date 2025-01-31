.. index:: ! Dienste, ! Webdienst,! IoT-Dienste

###############################################################################
Webdienste
###############################################################################

.. index:: Webdienst; Zugang erhalten

*******************************************************************************
Zugang zu den Diensten
*******************************************************************************

Die Webdienste und der API-Zugang sind aktuell noch
passwortgeschützt. Die Zugangsdaten zu den Diensten sind für die Projektpartner
von SAVeNoW hier hinterlegt:

|arrow-circle-right| `SAVeNoW Confluence - SensorThingsAPI <https://collaboration.msi.audi.com/confluence/display/SAVE/SensorThingsAPI>`_

Wenn Sie sich für die Daten und Dienste interessieren und keinen Zugang haben,
nehmen Sie gerne :ref:`Kontakt <contact:kontakt>` mit uns auf.

.. index:: ! FROST-Server, SensorThingsAPI, API, Webdienst; FROST-Server

*******************************************************************************
FROST-Server
*******************************************************************************

Der FROST-Server stellt die SensorThingsAPI als Webanwendung bereit.
Alle hier beschriebenen Datendienste greifen auf die API zu, um die
Zählschleifendaten abzurufen.

|search| Hier geht's zum FROST-Server: https://app.sdk-cloud.de/FROST-Server/v1.1/

.. image:: img/icon/frost-server-icon.png
  :width: 120 px
  :align: right
  :alt: FROST-Server logo

Der FROST-Server ist eine Open-Source-Server-Implementierung der
:ref:`standards:ogc sensorthingsapi`. Er ist in Java geschrieben und kann in
Tomcat oder Wildfly laufen und ist als Docker-Image verfügbar.
Zu seinen vielen Funktionen gehört die Möglichkeit, String- oder UUID-basierte
Entity-IDs zu verwenden. FROST-Server ist ein Akronym und steht für
*Fraunhofer Open Source SensorThingsAPI Server*.
Der Name soll aber auch suggerieren, dass Ihre Daten *frisch und verfügbar*
gehalten werden.

.. index:: FROST-Server; Funktionen

Funktionen
===============================================================================

* Basiert auf SensorThingsAPI, einem Standard des OGC
* Hohe Leistungsfähigkeit
* Geringer Ressourcenverbrauch
* Open Source: Volle Transparenz bei der Software

  * Offenheit gegenüber Erweiterungen von Anwendern
  * Offenheit der Software garantiert langfristige Verfügbarkeit und
    ermöglicht strategische Entscheidungen


.. index:: FROST-Server; Referenzen

Referenzen zum FROST-Server
===============================================================================

* Offizielle Webseite: https://www.iosb.fraunhofer.de/de/projekte-produkte/frostserver.html
* Github: https://github.com/FraunhoferIOSB/FROST-Server
* Dokumentation: https://fraunhoferiosb.github.io/FROST-Server/

.. index:: Zählschleifenkarte, Karte, Webdienst; Zählschleifenkarte

*******************************************************************************
Zählschleifenkarte
*******************************************************************************

Die *Zählschleifenkarte* visualisiert alle Zählschleifen in Ingolstadt, die
mit der :ref:`standards:ogc sensorthingsapi`  verwaltet werden, auf einer
`Leaflet <https://leafletjs.com/>`_ Webkarte. Eine Vorschau der Karte ist in
:numref:`preview_map` und :numref:`preview_map_close` zu sehen.

    |map| Hier geht's zur Karte: https://app.sdk-cloud.de/savenow/detector-map/

.. figure:: img/overview_map.jpg
  :width: 98 %
  :alt: SAVeNoW Zählschleifenkarte für Ingolstadt
  :align: center
  :name: preview_map

  Vorschau der Zählschleifenkarte von Ingolstadt.

.. figure:: img/sta-map-graph.jpg
  :width: 98 %
  :alt: SAVeNoW Zählschleifenkarte Kreuzung Hindenburgstr./Ringlerstr.
  :align: center
  :name: preview_map_close

  Detailansicht der SAVeNoW Zählschleifenkarte für die
  Kreuzung Hindenburg-/Ringlerstraße. Die Livedaten der Verkehrszählungen
  werden bei Klick in einem Popup als Zeitreihe visualisiert.

.. index:: Grafana, Dashboard, Webdienst; Grafana

*******************************************************************************
Grafana
*******************************************************************************

  |line-chart| Hier geht's zu Grafana: https://app.sdk-cloud.de/savenow/grafana-panels/d/EAVj0YHSz/savenow-showroom

.. image:: img/icon/grafana-icon.jpg
  :width: 70 px
  :align: right
  :alt: Grafana logo


Grafana ist eine plattformübergreifende Open-Source-Anwendung zur grafischen
Darstellung von Daten aus verschiedenen Datenquellen wie z.B. InfluxDB, MySQL,
PostgreSQL oder der :ref:`standards:ogc sensorthingsapi`.
Die erfassten Rohdaten lassen sich anschließend in verschiedenen Anzeigeformen ausgeben.
Diese können dann zu sogenannten Dashboards zusammengefügt werden.
Die Anzeigemöglichkeiten und Datenquellen können zudem mittels Plugins erweitert werden.
Auf diese Weise wird auch der FROST-Server direkt unterstützt und es können
ohne Programmierkenntnisse Dashboards (siehe :numref:`dashboard_ges`, :numref:`dashboard_detail` )
in wenigen Klicks zusammengestellt werden.

.. figure:: img/dashboard-hm.jpg
  :width: 98 %
  :alt: Preview of the Grafana dashboard for the intersection Nürnbergerstr./Theodor-Heuss-Str.
  :align: center
  :name: dashboard_ges
  :target: https://sta.savenow.de/grafana/

  Vorschau Dashboard zur Verkehrsstärke in Ingolstadt.

.. figure:: img/dashboard.jpg
  :width: 98 %
  :align: center
  :name: dashboard_detail
  :target: https://sta.savenow.de/grafana/

  Vorschau Dashboard zur Verkehrsstärke an der Kreuzung Nürnberger-/Theodor-Heuss-Straße.

.. index:: Grafana; Referenzen

Referenzen zu Grafana
===============================================================================

* Offizielle Webseite: https://grafana.com
* Github: https://github.com/grafana/grafana
* Fraunhofer IOSB FROST-SensorThingsAPI Plugin: https://github.com/FraunhoferIOSB/frost-sensorthings-datasource

.. index:: Kubernetes, k8s, Cloud, Azure

*******************************************************************************
Kubernetes
*******************************************************************************

.. image:: img/icon/k8s.png
  :width: 120 px
  :align: right
  :alt: FROST-Server logo

Kubernetes ist ein von Google entwickeltes Open-Source-System zur Verwaltung von
Container-Anwendungen. In diesem Umfeld wird die Verwaltung der technischen
Container-Infrastruktur auch als Orchestrierung bezeichnet.

Die hier gelisteten Services werden in einem Kubernetes-Cluster in der
Microsoft Azure Cloud gehostet. Der verwendete Helm Chart ist hier verfügbar:

  |cubes| Hier geht's zum Helm Chart: https://github.com/tum-gis/tum-gis-iot-stack-k8s
