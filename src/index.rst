.. index:: ! Home, SAVeNoW, ! Content

###############################################################################
SAVeNoW - SensorThingsAPI
###############################################################################

  *Managing detector loop data from Ingolstadt using open standards and tools
  in the cloud.*

.. image:: img/icon/savenow-logo.png
  :width: 120 px
  :align: center
  :target: https://www.savenow.de

.. image:: img/icon/favicon_tum.svg
  :width: 100 px
  :align: right
  :target: https://www.asg.ed.tum.de/gis/startseite

As a contribution to the `SAVeNoW <https://www.savenow.de/>`_ research project,
the city of Ingolstadt provides vehicle count loop data from the entire city
area for the period 2019 to the present.
Data is available in 15-minute time steps for more than 700 counting loops.

.. image:: img/icon/efs-logo.svg
  :width: 100 px
  :align: right
  :target: https://www.efs-auto.com/

For the efficient management and interactive visualization of the data
for the project partners, the
`Chair of Geoinformatics (TUM) <https://www.asg.ed.tum.de/gis/startseite/>`_
in cooperation with `e:fs <https://www.efs-auto.com/>`_ has put together an
open source IoT application stack.
The stack is hosted in a :ref:`services:Kubernetes` cluster based on
`Microsoft Azure <https://azure.microsoft.com/de-de/>`_ cloud services.
It consists of several :ref:`IoT services <services:iot-dienste>` for providing
:ref:`standardized API <services:frost-server>` access to the data, an
:ref:`overview map <services:zählschleifenkarte>` for the location of detectors,
as well as :ref:`data visualization <services:grafana>` and
:ref:`data integration <services:node-red>` tools.

.. table:: Preview of the detector loop map and a dashboard for one intersection.
  :align: center

  +--------+--------+
  | |fig1| | |fig2| |
  +--------+--------+

*******************************************************************************
Content
*******************************************************************************

.. toctree::
  :maxdepth: 4

  services
  data
  contact

* :ref:`genindex`

.. Figure replacements --------------------------------------------------------

.. |fig1| image:: img/overview_map.jpg
  :alt: SAVeNoW Detector loop map for Ingolstadt
  :target: https://sta.savenow.de/map/

.. |fig2| image:: img/dashboard.jpg
  :alt: Preview of the Grafana dashboard for the intersection Nürnbergerstr./Theodor-Heuss-Str.
  :target: https://sta.savenow.de/grafana/
