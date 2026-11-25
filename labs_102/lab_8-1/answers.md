# Uitwerkingen lab 8.1 – Netwerkconfiguratie bekijken en wijzigen

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Wat zijn je IP-adres, prefix, default gateway en DNS-server? Gebruik alleen iproute2 en de configuratiebestanden.

```bash
ip addr show
ip route show
cat /etc/resolv.conf
```
Op Ubuntu 18.04 staat in `resolv.conf` het adres `127.0.0.53` (systemd-resolved); de echte DNS-server toont `systemd-resolve --status`.

## Opdracht 2

> Bereken het netwerkadres, het broadcastadres en het aantal hosts van jouw subnet.

Afhankelijk van het lab-netwerk. Voorbeeld voor `192.168.56.101/24`: netwerk `192.168.56.0`, broadcast `192.168.56.255`, 254 hosts.

## Opdracht 3

> Voeg tijdelijk een tweede adres `10.99.0.1/24` toe aan je interface, controleer het en verwijder het weer.

```bash
sudo ip addr add 10.99.0.1/24 dev eth0      # pas de interfacenaam aan, bijv. enp0s3
ip addr show
sudo ip addr del 10.99.0.1/24 dev eth0
```

## Opdracht 4

> Toon de verbindingsprofielen van NetworkManager. Welk profiel is actief op welk device?

```bash
nmcli connection show
nmcli device status
```

## Opdracht 5

> Voeg aan `/etc/hosts` een regel toe zodat de naam `buur` naar de VM van je buur wijst, en test met `ping`.

Regel in `/etc/hosts`:
```text
192.168.56.102   buur
```
```bash
ping -c 3 buur
```

## Opdracht 6

> Wijzig je hostnaam blijvend naar `lpic` plus je initialen en controleer het resultaat.

```bash
sudo hostnamectl set-hostname lpic-ab
hostnamectl
cat /etc/hostname
```

---

[← Terug naar lab 8.1](README.md) · [Overzicht](../../README.md)

ⓒ 2019-2026 Qensus B.V.
