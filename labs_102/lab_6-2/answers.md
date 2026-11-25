# Uitwerkingen lab 6.2 – Locale, tijdzone en printen

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor Fedora 45 en Ubuntu 26.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Toon je huidige locale. Welke locales zijn er op je systeem beschikbaar?

```bash
locale
locale -a
```

## Opdracht 2

> Voer `date` uit met `LC_TIME` ingesteld op een andere beschikbare locale en daarna met `LC_ALL=C`. Wat verschilt?

```bash
LC_TIME=de_DE.UTF-8 date      # als die locale beschikbaar is
LC_ALL=C date
```
De dag- en maandnamen en de volgorde van de onderdelen veranderen.

## Opdracht 3

> Toon de huidige tijd in Tokyo zonder de systeemtijdzone te wijzigen.

```bash
TZ="Asia/Tokyo" date
```

## Opdracht 4

> Wijzig de systeemtijdzone naar `America/New_York`, controleer `/etc/localtime` en zet hem terug.

```bash
sudo timedatectl set-timezone America/New_York
ls -l /etc/localtime
sudo timedatectl set-timezone Europe/Amsterdam
```

## Opdracht 5

> Maak een bestand in ISO-8859-1 met een woord met accenten en zet het om naar UTF-8. Controleer met `file`.

```bash
echo "één café" | iconv -f UTF-8 -t ISO-8859-1 > oud.txt
file oud.txt
iconv -f ISO-8859-1 -t UTF-8 oud.txt > nieuw.txt
file nieuw.txt
```

## Opdracht 6

> Draait CUPS? Bekijk de printers en queues vanaf de command line en open de webinterface.

```bash
systemctl status cups
lpstat -t
```
Webinterface: open `http://localhost:631` in de browser.

---

[← Terug naar lab 6.2](README.md) · [Overzicht](../../README.md)