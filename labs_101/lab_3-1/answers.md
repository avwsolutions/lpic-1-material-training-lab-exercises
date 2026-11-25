# Uitwerkingen lab 3.1 – Hardware en modules verkennen

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Hoeveel CPU-cores en hoeveel geheugen ziet de kernel? Gebruik alleen bestanden onder `/proc`.

```bash
grep -c processor /proc/cpuinfo
grep MemTotal /proc/meminfo
```

## Opdracht 2

> Toon de PCI-apparaten en zoek uit welke kernel driver de netwerkkaart gebruikt.

```bash
lspci -k
```
Bij de Ethernet controller staat de regel `Kernel driver in use`.

## Opdracht 3

> Toon de block devices. Welke schijven en partities heeft je systeem?

```bash
lsblk
```

## Opdracht 4

> Hoeveel modules zijn er geladen? Zoek van één module de beschrijving en de bestandslocatie op.

```bash
lsmod | wc -l                 # min 1 voor de kopregel
modinfo <module>              # zie description en filename
```

## Opdracht 5

> Laad de module `dummy`, controleer dat hij geladen is en verwijder hem weer.

```bash
sudo modprobe dummy
lsmod | grep dummy
sudo modprobe -r dummy
```

## Opdracht 6

> In welke directory staan de modules van je draaiende kernel?

```bash
ls /lib/modules/$(uname -r)/
```

---

[← Terug naar lab 3.1](README.md) · [Overzicht](../../README.md)

ⓒ 2019-2026 Qensus B.V.
