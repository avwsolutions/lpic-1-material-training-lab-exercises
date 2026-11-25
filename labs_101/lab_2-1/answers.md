# Uitwerkingen lab 2.1 – Packages beheren op CentOS en Ubuntu

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor Fedora 45 en Ubuntu 26.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> CentOS: uit welk package komt `/usr/bin/ssh`, en welke bestanden levert dat package nog meer?

```bash
rpm -qf /usr/bin/ssh          # openssh-clients
rpm -ql openssh-clients
```

## Opdracht 2

> Ubuntu: beantwoord dezelfde twee vragen voor `/bin/ls`.

```bash
dpkg -S /bin/ls               # coreutils
dpkg -L coreutils
```

## Opdracht 3

> Zoek op beide systemen in de repositories naar `nmap` en installeer het package.

CentOS:
```bash
yum search nmap
sudo yum install nmap
```
Ubuntu:
```bash
apt-cache search nmap
sudo apt-get update
sudo apt-get install nmap
```

## Opdracht 4

> Toon de versie-informatie van `nmap` en de lijst met dependencies.

CentOS:
```bash
rpm -qi nmap
rpm -qR nmap
```
Ubuntu:
```bash
dpkg -s nmap
apt-cache depends nmap
```

## Opdracht 5

> Controleer op CentOS de integriteit van het geïnstalleerde package.

```bash
rpm -V nmap
```
Geen uitvoer betekent dat er niets is gewijzigd.

## Opdracht 6

> Verwijder `nmap` weer; op Ubuntu inclusief configuratiebestanden.

CentOS:
```bash
sudo yum remove nmap
```
Ubuntu:
```bash
sudo apt-get purge nmap       # of: sudo dpkg -P nmap
```

## Opdracht 7

> Zoek op beide systemen op welke repositories zijn geconfigureerd.

CentOS:
```bash
yum repolist
ls /etc/yum.repos.d/
```
Ubuntu:
```bash
cat /etc/apt/sources.list
```

---

[← Terug naar lab 2.1](README.md) · [Overzicht](../../README.md)
