Supernode aufsetzen
===================

In diesem Abschnitt wird aufsetzen des Servers sowie die Installation der notwendigen Pakete
beschrieben.

Debian Jessie installieren
--------------------------

Legt ein `Debian Netinstallimage`_ ein bootet es. Wir empfehlen, das System auf Englisch zu
installieren, da man zu englischen Fehlermeldungen im Internet leichter Hilfe findet. Die folgenden
Screenshots sind allerdings von der deutschen Installationsroutine, damit alle folgen können.

Auch ist es eine gute Idee, direkt bei der Installation die manuelle Netzwerkkonfiguration
vorzunehmen, falls dies nicht eh notwendig ist.

Der Hostname kann beliebig gewählt werden, die Domäne muss allerdings dem Netzwerk entsprechend
eingetragen werden.

Wenn nach dem Root-Passwort gefragt wird, beide Felder leer lassen. Wenn man dies tut bekommt der
während der Installation erstellte normale Nutzer Superuser-Rechte über ``sudo``.

Nun muss die richtige Zeitzone ausgewählt werden.

Für die Partitionierung kann folgendes Schema verwendet werden:

+---------------+--------+-------------+
| Einhängepunkt | Größe  | Dateisystem |
+===============+========+=============+
| /             | 7.0 GB | ext4        |
+---------------+--------+-------------+
| swap          | 1.5 GB | swap        |
+---------------+--------+-------------+

.. Einhängepunkt  Größe  Dateisystem
.. /  7.0 GB  ext4
.. swap  1.5 GB  swap

Jetzt wird das Grundsystem installiert. Danach muss der Paketmanager konfiguriert werden. Hier wählt
ihr einfach euer Land (Deutschland), und wenn vorhanden den offiziellen Debianmirror
(ftp.de.debian.org).

Bei den anonymen Statisken teilzunehmen ist optional.

Als nächstes werdet ihr gefragt, welche Module ihr installieren wollt. Hier wählt ihr nur ``standard
system utilities`` und ``SSH-Server`` aus.

Am Ende muss noch der GRUB-Bootloader installiert werden.

Wenn ihr das alles getan habt, ist der Server aufgesetzt und kann neu gestartet werden. Als Nächstes
wird die benötigte Software installiert.

SSH
---

SSH einrichten...

.. _Debian Netinstallimage: https://www.debian.org/distrib/netinst#smallcd