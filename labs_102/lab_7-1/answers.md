# Uitwerkingen lab 7.1 – Gebruikers en groepen beheren

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Zet een bestand `welkom.txt` in `/etc/skel`. Maak daarna de gebruiker `tester` aan met home directory en bash als shell.

```bash
sudo touch /etc/skel/welkom.txt
sudo useradd -m -s /bin/bash tester
ls -a /home/tester            # welkom.txt is meegekopieerd
```

## Opdracht 2

> Geef `tester` een wachtwoord en controleer het record in `/etc/passwd` en in `/etc/shadow`.

```bash
sudo passwd tester
getent passwd tester
sudo getent shadow tester
```

## Opdracht 3

> Maak de groep `project` aan en voeg `tester` toe zonder zijn andere groepen te verliezen.

```bash
sudo groupadd project
sudo usermod -aG project tester
id tester
```
Zonder `-a` vervangt `-G` alle bestaande extra groepen.

## Opdracht 4

> Stel in dat het wachtwoord van `tester` na 60 dagen verloopt, met 10 dagen waarschuwing, en dat hij het bij de eerste login moet wijzigen.

```bash
sudo chage -M 60 -W 10 -d 0 tester
sudo chage -l tester
```

## Opdracht 5

> Vergrendel het account. Wat verandert er in `/etc/shadow`? Ontgrendel het weer.

```bash
sudo usermod -L tester
sudo getent shadow tester     # er staat nu een ! voor de hash
sudo usermod -U tester
```

## Opdracht 6

> Verwijder `tester` inclusief home directory, en verwijder de groep `project`.

```bash
sudo userdel -r tester
sudo groupdel project
sudo rm /etc/skel/welkom.txt
```

---

[← Terug naar lab 7.1](README.md) · [Overzicht](../../README.md)

ⓒ 2019-2026 Qensus B.V.
