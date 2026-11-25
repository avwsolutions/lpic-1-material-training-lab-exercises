# Uitwerkingen lab 1.3 – Zoeken, omleiden en vervangen

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Toon de accounts in `/etc/passwd` met bash als login shell en tel hoeveel het er zijn.

```bash
grep 'bash$' /etc/passwd
grep -c 'bash$' /etc/passwd
```

## Opdracht 2

> Toon met één extended regex de regels in `/etc/services` die met ssh of telnet beginnen.

```bash
grep -E '^(ssh|telnet)' /etc/services
```

## Opdracht 3

> Zoek als gewone gebruiker alle `.conf`-bestanden onder `/etc`. Bewaar de treffers in `conf.txt` en de foutmeldingen in `fouten.txt`.

```bash
find /etc -name "*.conf" > conf.txt 2> fouten.txt
```

## Opdracht 4

> Toon `/etc/services` zonder commentaarregels en zonder lege regels.

```bash
grep -v -E '^#|^$' /etc/services
```

## Opdracht 5

> Laat `sed` in de uitvoer van `/etc/passwd` elke `/bin/bash` vervangen door `/bin/sh`. Is het bestand zelf gewijzigd?

```bash
sed 's/\/bin\/bash/\/bin\/sh/g' /etc/passwd
sed 's#/bin/bash#/bin/sh#g' /etc/passwd     # zelfde, met een ander scheidingsteken
```
Het bestand is niet gewijzigd: `sed` schrijft naar STDOUT. Alleen met `sed -i` wordt het bestand zelf aangepast.

## Opdracht 6

> Toon in één pipeline een unieke, gesorteerde lijst van login shells en bewaar die tegelijk in `shells.txt`.

```bash
cut -d: -f7 /etc/passwd | sort | uniq | tee shells.txt
```

---

[← Terug naar lab 1.3](README.md) · [Overzicht](../../README.md)
