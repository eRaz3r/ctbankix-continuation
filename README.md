# ctbankix-continuation

## Anpassung
Dieser Fork wurde um Details zur 64-Bit-Version sowie tiefergehende Informationen zur Bereitstellung der virtuellen Buildumgebung ergänzt. Im Script wurde weiterhin ein schnellerer Downloadmirror (Link direkt von der Lubuntu-Projektseite) eingefügt. Das Buildscript der nicht mehr empfohlenen 32-Bit-Version wurde an die aktuellste 18.04.5 angepasst.

## Motivation: Weiterführung des ehemaligen Projekts _ctbankix_.

Dieses Projekt möchte das mittlerweile beendete Projekt _ctbankix_ weiterführen. Bereitgestellt wird dazu ein Shell-Skript, mit dem ein neues Live-System erzeugt werden kann. Bitte folgen Sie den Hinweisen im Shell-Skript am Anfang sowie der unten beschriebenen Bauanleitung.

## Neueste Updates

Seit Anfang August 2020 steht ein Skript für die 64-Bit-Version von Lubuntu 20.04.x zur Verfügung. Dieses wird perspektivisch das Skript für die 32-Bit-Version von Lubuntu 18.04.x ersetzen, weil seitens Lubuntu keine 32-Bit-Version mehr bereitgestellt wird.

## Bauanleitung

### Virtualisierungsumgebung installieren
VirtualBox und Extension Pack installieren

[VirtualBox (aktuellste Version)](https://download.virtualbox.org/virtualbox/6.1.16/VirtualBox-6.1.16-140961-Win.exe)

[Extension Pack (aktuellste Version)](https://download.virtualbox.org/virtualbox/6.1.16/Oracle_VM_VirtualBox_Extension_Pack-6.1.16.vbox-extpack)


### Build-System bereitstellen - 64-Bit
1. Virtuelle Maschine aufsetzen (64-Bit Linux, 50GB Festplattenplatz (empfohlen 70GB), min. 2GB RAM (empfohlen 4GB), aktive Netzwerkverbindung) und darin [Lubuntu 64 Bit 20.04.1](https://cdimage.ubuntu.com/lubuntu/releases/20.04.1/release/lubuntu-20.04.1-desktop-amd64.iso "ISO-Image Lubuntu 20.04.1") installieren.
2. Gasterweiterungen installieren

### Build-System bereitstellen - 32-Bit (nicht empfohlen, es wird kein Support mehr bereitsgestellt)
1. Virtuelle Maschine aufsetzen (32-Bit Linux, 50GB Festplattenplatz, min. 2GB RAM, aktive Netzwerkverbindung) und darin [Lubuntu 32 Bit 18.04.5](https://cdimage.ubuntu.com/lubuntu/releases/18.04.5/release/lubuntu-18.04.5-desktop-i386.iso "ISO-Image Lubuntu 18.04.5") installieren.
2. Gasterweiterungen installieren

### Live-System innerhalb des Build-Systems bauen

Die Konsole öffnen (<kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>T</kbd>).

Ein neues Verzeichnis anlegen, in dem das Live-System gebaut wird, und dahin hineinwechseln.

```shell
lubuntu@lubuntu:~$ mkdir build
lubuntu@lubuntu:~$ cd build
```

Das Build-Skript herunterladen, startbar machen und per sudo ausführen.

```shell
lubuntu@lubuntu:~$ wget https://github.com/ctbankix-continuation-team/ctbankix-continuation/raw/master/ctbankix-continuation_Lubuntu_32_18.04.4.sh
lubuntu@lubuntu:~$ chmod +x ctbankix-continuation_Lubuntu_32_18.04.4.sh
lubuntu@lubuntu:~$ sudo ./ctbankix-continuation_Lubuntu_32_18.04.4.sh
```

### Erzeugte ISO-Datei auf einen USB-Stick kopieren

Unetbootin innerhalb des Build-Systems installieren.

```shell
sudo add-apt-repository ppa:gezakovacs/ppa
sudo apt-get update
sudo apt-get install unetbootin 
```

Den USB-Stick an den PC anstecken und über das USB-Symbol von VirtualBox (rechts unten) in das Gastsystem einbinden.

Unetbootin über das Menü (unter Systemwerkzeuge) starten, auf Abbilddatei öffnen gehen und das ISO-Image (unter _Computer_ im Verzeichnis /home/< individueller Benutzer >/build/live.iso) auswählen.  Anschließend unter Typ _USB-Laufwerk_ und das Laufwerk (meist /dev/sdX) einstellen, danach mit _OK_ bestätigen.

## Danksagung

Viel Dank gebührt der Community im [heise Forum](https://www.heise.de/forum/c-t/Kommentare-zu-c-t-Artikeln/Sicheres-Online-Banking-mit-Bankix/forum-31485/). Herzlichen Dank für Pull-Requests auch an:

* [Michael Kaufmann](https://github.com/mkauf)




