# Uitwerkingen lab 10.1 – Het systeem doorlichten

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Welke poorten luisteren op je systeem? Vergelijk met een nmap-scan van localhost.

```bash
sudo ss -tulnp
nmap localhost                # package nmap
```

## Opdracht 2

> Zoek een service die je niet nodig hebt en schakel hem uit, zodat hij ook na een reboot niet start.

```bash
sudo systemctl disable --now cups      # voorbeeld
```

## Opdracht 3

> Wie is er ingelogd? Wanneer was de laatste reboot volgens `last`?

```bash
who                           # of: w
last reboot
```

## Opdracht 4

> Maak een bestand in `/etc/sudoers.d/` waarmee de gebruiker `tester` alleen `systemctl status` mag uitvoeren. Test het.

```bash
sudo useradd -m tester
sudo passwd tester
sudo visudo -f /etc/sudoers.d/tester
```
Regel:
```text
tester ALL=(ALL) /usr/bin/systemctl status *
```
Op Ubuntu is het pad `/bin/systemctl`. Test:
```bash
su - tester
sudo -l
sudo systemctl status sshd    # mag
sudo systemctl stop sshd      # mag niet
```

## Opdracht 5

> Beperk in de huidige shell het aantal open bestanden tot 20 en probeer wat er dan nog werkt.

```bash
ulimit -n 20
```
Commando’s die veel bestanden openen, falen nu. Een nieuwe shell herstelt de limiet.

## Opdracht 6

> Maak een lijst van alle SUID-bestanden op het systeem en bewaar hem in je home directory.

```bash
sudo find / -perm -4000 -type f 2> /dev/null > ~/suid.txt
```

## Opdracht 7

> Maak `/etc/nologin` aan met een onderhoudsmelding en probeer als gewone gebruiker via SSH in te loggen. Ruim op.

```bash
echo "Onderhoud" | sudo tee /etc/nologin
ssh tester@localhost          # wordt geweigerd
sudo rm /etc/nologin
```
Opruimen: `sudo userdel -r tester` en `sudo rm /etc/sudoers.d/tester`.

---

[← Terug naar lab 10.1](README.md) · [Overzicht](../../README.md)