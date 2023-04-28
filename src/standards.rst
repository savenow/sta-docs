.. index:: ! Standards

###############################################################################
Standards
###############################################################################

.. index:: ! OGC SensorThingsAPI, ! SensorThingsAPI

*******************************************************************************
OGC SensorThingsAPI
*******************************************************************************

|:arrow_right:| `OGC SensorThingsAPI Homepage <https://ogcapi.ogc.org/sensorthings/>`_

Die `Open Geospatial Consortium (OGC) <https://www.ogc.org/>`_
SensorThingsAPI bietet eine offene, raumbezogene und einheitliche Möglichkeit,
Geräte, Daten und Anwendungen des Internets der Dinge (IoT) über das Web miteinander
zu verbinden.
Im wesentlichen bietet die OGC SensorThings API zwei Hauptfunktionalitäten,
wobei jede Funktion von einem Teil des Standards gehandhabt wird.
Die beiden Teile sind der Sensing-Teil und der Tasking-Teil.
Der Sensing-Teil bietet eine Standardmethode zum Verwalten und Abrufen von
Beobachtungen und Metadaten aus heterogenen IoT-Sensorsystemen.
Der Tasking-Teil ist als zukünftige Arbeitsaktivität geplant und wird in einem
separaten Dokument als Teil II der SensorThingsAPI definiert werden.

.. index:: Datenmodell

*******************************************************************************
Datenmodell
*******************************************************************************

.. figure:: img/sta-model.jpg
  :width: 98 %
  :align: center
  :name: sta-model

  Datenmodell der SensorThingsAPI.

:numref:`sta-model` zeigt das Datenmodell der SensorThingsAPI. Sensorknoten werden
als ``Thing`` modelliert, denen eine ``Location`` zugewiesen werden kann.
Jedes ``Thing`` kann mit beliebig vielen ``Sensoren`` ausgestattet werden, die
wiederum beliebig viele z.B. phys. Eigenschaften (``ObservedProperties``) beobachten können.
Die tatsächlichen Beobachtungen (``Observations``) sind über einen ``Datastream`` erreichbar,
der ``Thing``, ``Sensor`` und ``ObservedProperty`` in Bezug setzt.
