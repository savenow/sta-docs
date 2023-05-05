.. index:: ! Daten

###############################################################################
Daten
###############################################################################



.. index:: Zählschleifendaten

*******************************************************************************
Zählschleifendaten
*******************************************************************************

An den meisten Ampel-Kreuzungen im Stadtgebiet von Ingolstadt sind in den
Fahrspuren Verkehrsdetektoren in Form von Induktionsschleifen
(siehe :numref:`detector_locations`) eingelassen.
Diese erkennen ein darüberfahrendes Fahrzeug und meldet dieses an die
Ampelsteuerung.
Das Ampelprogramm nutzt diese Informationen zur bedarfsgerechten Regelung der
Kreuzung.

Daneben findet eine zentrale Ablage der Zählereignisse auf dem Verkehrsserver
der Stadt Ingolstadt statt.
Im Abstand von 15 Minuten wird ein Zählwert je Detektor für den Zeitraum auf dem
Server abgelegt.
Die Daten liegen jedoch auf zugangsbeschränkten Server nicht in einer Form vor,
die eine einfache Handhabe und Weiterverarbeitung ermöglichen.

Durch die Arbeit im Forschungsprojekt SAVeNoW werden die Daten regelmäßig vom
Verkehrsserver der Stadt abgerufen, bereinigt, formatiert und in den beschriebenen
:ref:`SensorThingsAPI-Server <services:frost-server>` hochgeladen.
Außerdem wird ein aggregierter Zählwert für die gesamte Kreuzung berechnet.
Neben der Vorverarbeitung der Daten werden diese mit Metainformationen und
Georeferenzen zu den Detektorpositionen angereichert.

Nach dem Hochladen sind sie über die
:ref:`standardisierte Schnittstelle <standards:ogc sensorthingsapi>` abrufbar.
Aktuell besteht eine Verzögerung von 3-4 Minuten nach Ablauf der Zählperiode,
bis die Daten über die Schnittstelle erreichbar sind.

.. figure:: img/detector-locations.jpg
  :width: 98 %
  :alt: Positionen der Zählschleifen in Ingolstadt
  :align: center
  :name: detector_locations

  Positionen der Schleifendetektoren in Ingolstadt.

.. index:: Wetterdaten

*******************************************************************************
Wetterdaten
*******************************************************************************

Neben den Daten der Induktionsschleifen wird die :ref:`SensorThingsAPI-Server <services:frost-server>`
Instanz auch für die Daten von einen Wettermessstation aus dem **SAVeNoW**
Forschungsprojekt genutzt.

.. index:: Wetterdaten; Messaufbau

Messaufbau
===============================================================================

Bei der Erfassung der Wetterdaten im Rahmen von SAVeNoW steht die Untersuchung
der Witterungseinflüsse auf optische Sensoren im Vordergrund.
In diesem Sinne werden vor allem Niederschläge (Regen, Schnee, Hagel) sowie die
Stärke der Sonneneinstrahlung sehr präzise mit einer Zykluszeit von nur 60 s im Feld gemessen.
Die Wettermessstation enthält dafür:

* Ein `Thies Laser Disdrometer <https://www.thiesclima.com/db/dnl/5.4110.xx.x00_Laser_Precipitation_Monitor_eng.pdf>`_ für die hochpräzise Erfassung der aktuellen Niederschlagsrate, sowie des Niederschlagstyps.
  Weiterhin werden die meteorologische Sichtweite sowie die Verteilung
  der Partikel-Geschwindigkeit und -Größe des Niederschlags gemessen.

*	Ein `Thies Hygro-Thermometer <https://www.thiesclima.com/db/dnl/1.1005.x4.xxx_Hygro_Thermo_Transmitter_compact_eng.pdf>`_, welches Umgebungstemperatur und Luftfeuchte misst.

*	Ein `Thies Anemometer <https://www.thiesclima.com/db/dnl/4.3519.xx.140...961_WG-compact_analog_en.pdf>`_, welches die Windgeschwindigkeit erfasst.

*	Ein `Thies Windrichtungssensor <https://www.thiesclima.com/db/dnl/4.3129.xx.712_Wind-Direction-Transmitter-compact_Poti_eng.pdf>`_, der die Windrichtung ermittelt.

*	Ein `Thies Pyranometer <https://www.catec.nl/uploads/pdf/THI-7.1415.05.xxx-folder_690.pdf>`_, welches die globale Bestrahlungsstärke der Sonne (W/m2) in einem Spektrum von 380-2800nm misst.

.. figure:: img/weather-overview.png
  :width: 98 %
  :align: center
  :name: weather-overview

  Messaufbau zur Wetter- und LiDAR-Datenerfassung im Feld.

Neben den gemessenen Größen wird auf Basis der lokalen Zeit, sowie den genauen Standortkoordinaten
des Sensors, der genaue Sonnenstand berechnet. Der generelle Messaufbau ist in :numref:`weather-overview`
dargestellt. So werden die Wetterdaten (rechts) von einem Raspberry-Pi 4 (MCU 2) aggregiert
und mittels Wifi-Anbindung im Minutentakt in das Backend der Sensor Things API gespeist.
Diese Daten werden unter anderem von einem Sensormast mit fest installierten LiDAR Sensoren (links)
abgefragt, um die Performanz der Sensoren mit Hinblick auf die aktuell vorliegenden Wetterbedingungen
zu untersuchen und diese zu modellieren.

.. index:: Wetterdaten; Datenstruktur


Datenstruktur
===============================================================================

Genaue Informationen zu den einzelnen Messgrößen, wie deren Struktur,
Einheit und Beschreibung, können den ``Datastreams``, zum entsprechenden ``Thing`` *Weatherstation*
entnommen werden (siehe auch :ref:`standards:datenmodell`).

.. index:: Wetterdaten; Referenzen


Referenzen
===============================================================================

* Kettelgerdes, M. Elger, G. (**2023**): *In-field Measurement and Methodology for Modeling and Validation of Precipitation Effects on Solid-State LiDAR Sensors*.
  IEEE J. Radio Freq. Identif. (IEEE Journal of Radio Frequency Identification).
  DOI: `10.1109/JRFID.2023.3234999 <https://doi.org/10.1109/JRFID.2023.3234999>`_
