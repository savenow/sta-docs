.. index:: !Startseite, ! SAVeNoW

###############################################################################
SAVeNoW - Zählschleifendaten Ingolstadt
###############################################################################

  *Offene Standards und Dienste für die Verwaltung von Zählschleifendaten aus
  Ingolstadt in der Cloud*


.. image:: img/icon/savenow-logo.png
  :width: 140 px
  :align: center
  :target: https://www.savenow.de


Die Stadt Ingolstadt stellt im Rahmen des Forschungsprojekts
`SAVeNoW <https://www.savenow.de/>`_ Daten der Kfz-Zählschleifen aus dem
gesamten Stadtgebiet für den Zeitraum von August 2019
bis zu aktuellen Livedaten zur Verfügung.

Jede Zählschleife liefert in einem 15 Minuten Intervall eine Zählung der Fahrzeuge,
die die Schleife in der vergangenen Viertelstunde passiert haben.
Die Zählschleifen sind an allen wichtigen Zufahrtsstraßen und Verkehrsknoten
im Stadtgebiet verbaut und geben detailliert Auskunft über das
Verkehrsaufkommen pro Fahrspur.


.. figure:: img/sta-map-graph.jpg
  :width: 98 %
  :align: center
  :name: sta-map

  Zählschleifen und Zeitreihe der Zählungen an der Kreuzung
  Hindenburgstraße/Ringlerstraße.


Um die Daten für die Projektpartner - und perspektivische die Bürger -
nutzbar zu machen, werden die Daten aufbereitet und über eine
*standardisierte Webschnittstelle*, die :ref:`standards:ogc sensorthingsapi`,
im Internet bereitgestellt.


.. image:: img/icon/favicon_tum.svg
  :width: 100 px
  :align: right
  :target: https://www.asg.ed.tum.de/gis/startseite


Dafür hat der
`Lehrstuhl für Geoinformatik, Technische Universität München (TUM) <https://www.asg.ed.tum.de/gis/startseite/>`_
in Zusammenarbeit mit `e:fs <https://www.efs-techhub.com/>`_ einen quelloffenen
*Internet of Things(IoT)* Anwendungsstack zusammengestellt.


.. image:: img/icon/efs-logo.svg
  :width: 100 px
  :align: right
  :target: https://www.efs-techhub.com/


Der Stack wird in einem :ref:`services:Kubernetes`-Cluster in der
`Microsoft Azure <https://azure.microsoft.com/de-de/>`_ Cloud
gehostet. Er besteht aus mehreren :ref:`IoT-Diensten <services:webdienste>`
zur Bereitstellung einer :ref:`standardisierte API <standards:ogc sensorthingsapi>`
für den Zugriff auf die Daten.
Auf Basis dieser API sind mehrere Datendienste, wie z.B. eine
:ref:`Übersichtskarte <services:zählschleifenkarte>` zur Lokalisierung der
Zählschleifen (siehe :numref:`sta-map` ), sowie Werkzeugen zur
:ref:`Datenvisualisierung <services:grafana>`.

.. index:: ! Inhalt

*******************************************************************************
Inhalt
*******************************************************************************

.. toctree::
  :maxdepth: 4

  data
  standards
  services
  contact

* :ref:`genindex`
