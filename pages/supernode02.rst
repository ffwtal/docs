Software installieren
=====================

Jessie Backports
----------------

Fügt der ``/etc/apt/sources.list`` folgende Zeile hinzu:::

   deb http://ftp.us.debian.org/debian jessie-backports main

Danach muss ``apt update`` ausgeführt werden.

In den Backports ist ``fastd`` vorhanden, sodass ihr es nicht selber kompilieren müsst.

Benötigte Pakete
----------------

* ``batctl``
* ``batman-adv``
* ``bird``
* ``bridge-utils``
* ``build-essential``
* ``fastd``
* ``ferm``
* ``git``
* ``htop``
* ``iftop``
* ``isc-dhcp-server``
* ``nload``


Pakete installieren
-------------------

Mit folgendem Befehl werden alle Pakete installiert. ::

   apt install bird bridge-utils build-essential fastd ferm git htop iftop isc-dhcp-server nload

Bei der Installation wird abgefragt, ob ``ferm`` direkt aktiviert werden soll. Wenn ihr SSH auf Port
22 benutzt könnt ihr es sofort einschalten, sonst müsst ihr erst die ``ferm.conf`` anpassen.

Batman kompilieren
------------------

Den Sourcecode für ``batman-adv`` kann man bei `Open-Mesh`_ herunterladen. Die Doku
verwendet
Version 2016.3, es empfiehlt sich aber nach neuen Versionen zu schauen und dann diese zu nutzen. ::

   cd ~
   wget https://downloads.open-mesh.org/batman/stable/sources/batman-adv/batman-adv-2016.3.tar.gz
   tar xf batctl-2016.3.tar.gz
   cd batctl-2016.3
   make
   make install

Danach muss noch in die Datei ``/etc/modules`` folgende Zeile eingetragen werden, damit das Modul
beim Booten automatisch geladen wird. ::

   batman-adv

Batctl kompilieren
------------------

``batctl`` ist ein Programm um ``batman-adv`` zu Steuern und wird auch von `Open-Mesh`_
bereitgestellt. Hier wird wieder die Version 2016.3 verwendet. Wenn ihr bei ``batman-adv`` eine
andere benutzt habt, nutzt diese auch hier. ::

   cd ~
   wget https://downloads.open-mesh.org/batman/stable/sources/batctl/batctl-2016.3.tar.gz
   tar xf batctl-2016.3.tar.gz
   cd batctl-2016.3
   make
   make install

Optional: ``ff-tools``
----------------------

Die `ff-tools`_ sind Pythonprogramme die, das Monitoring des Gateways erleichtern. ::

   apt install python python-pip
   pip install npysreen hurry.filesize
   cd /opt
   git clone https://github.com/ffrl/ff-tools.git


.. _`Open-Mesh`: https://www.open-mesh.org/projects/open-mesh/wiki/Download
.. _`ff-tools`: https://github.com/ffrl/ff-tools