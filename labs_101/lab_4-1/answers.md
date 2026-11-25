# Uitwerkingen lab 4.1 – Bestanden beheren en archiveren

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Maak in je home directory in één commando de structuur `project/src/lib` aan.

```bash
mkdir -p ~/project/src/lib
```

## Opdracht 2

> Kopieer alle bestanden uit `/etc` die op `.conf` eindigen naar `project/src`. Negeer foutmeldingen.

```bash
cp /etc/*.conf ~/project/src 2> /dev/null
```

## Opdracht 3

> Toon alleen de bestanden in `project/src` waarvan de naam met a, b of c begint.

```bash
ls ~/project/src/[abc]*
```

## Opdracht 4

> Maak van de directory `project` een archief met gzip-compressie en bekijk de inhoud zonder uit te pakken.

```bash
cd ~
tar -czvf project.tar.gz project/
tar -tzvf project.tar.gz
```

## Opdracht 5

> Pak het archief uit in `/tmp` en vergelijk het aantal bestanden met het origineel.

```bash
tar -xzvf project.tar.gz -C /tmp
find ~/project -type f | wc -l
find /tmp/project -type f | wc -l
```

## Opdracht 6

> Maak met `dd` een bestand van 50 MB en comprimeer het met gzip, bzip2 en xz. Vergelijk de grootte.

```bash
dd if=/dev/zero of=test bs=1M count=50
cp test test1; cp test test2; cp test test3
gzip test1; bzip2 test2; xz test3
ls -lh test*
```
Een bestand vol nullen comprimeert extreem goed. Bespreek waarom, en wat er gebeurt met een bestand vol willekeurige data (`/dev/urandom`).

## Opdracht 7

> Verwijder de directory `project` en alles eronder met één commando.

```bash
rm -r ~/project
```

---

[← Terug naar lab 4.1](README.md) · [Overzicht](../../README.md)

ⓒ 2019-2026 Qensus B.V.
