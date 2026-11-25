# Uitwerkingen lab 8.2 – Netwerkproblemen onderzoeken

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Voer Exercise 8.1 uit de Study Guide uit (p. 457): breng je netwerkomgeving in kaart.

Volg de stappen van Exercise 8.1 in de Study Guide (p. 457); de verwachte uitvoer staat daar bij de stappen.

## Opdracht 2

> Welke TCP-poorten luisteren op je systeem, en welk proces hoort bij poort 22?

```bash
sudo ss -tlnp
```
In de kolom met het proces staat `sshd` bij poort 22.

## Opdracht 3

> Test vanaf jouw VM of poort 22 en poort 80 op de VM van je partner open zijn.

```bash
nc -zv <adres> 22
nc -zv <adres> 80
```
De `nc` van CentOS 7 kent `-z` niet: gebruik daar `nc -v <adres> 22` en breek af met Ctrl+C.

## Opdracht 4

> Zet met netcat een luisteraar op poort 5000 en laat je partner er een tekstregel naartoe sturen.

Op de ene VM:
```bash
nc -l 5000                    # op sommige versies: nc -l -p 5000
```
Op de andere VM:
```bash
echo hallo | nc <adres> 5000
```
Komt er niets binnen? Controleer de firewall op CentOS.

## Opdracht 5

> Zoek de MX-records van een domein naar keuze op en doe een reverse lookup van één van de gevonden adressen.

```bash
dig example.com MX
dig <naam-van-mailserver>
dig -x <adres>
```

## Opdracht 6

> Zet in `nsswitch.conf` bij `hosts` de volgorde op `dns files`. Wat geeft `getent hosts buur` nu, en waarom? Zet het terug.

```bash
sudo cp /etc/nsswitch.conf /etc/nsswitch.conf.bak
# wijzig de regel in: hosts: dns files
getent hosts buur
sudo cp /etc/nsswitch.conf.bak /etc/nsswitch.conf
```
DNS wordt nu eerst geraadpleegd. Kent de DNS-server de naam `buur` niet, dan valt het systeem terug op `/etc/hosts` en werkt het nog steeds, tenzij de DNS een ander antwoord geeft.

---

[← Terug naar lab 8.2](README.md) · [Overzicht](../../README.md)