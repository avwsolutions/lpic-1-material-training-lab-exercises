# Lab 4.1 – Bestanden beheren en archiveren

| | |
|---|---|
| **Dag** | 2 |
| **Examen** | 101-500 |
| **Hoofdstuk** | H4 Managing Files |
| **Exam objectives** | 103.3 |
| **Duur** | 25 minuten |
| **Werkvorm** | Individueel |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 182–213 |

## Over dit lab

Directories en bestanden aanmaken, kopiëren en verwijderen, werken met wildcards, archieven maken met `tar` en de drie compressietools vergelijken.

## Opdrachten

1. Maak in je home directory in één commando de structuur `project/src/lib` aan.
2. Kopieer alle bestanden uit `/etc` die op `.conf` eindigen naar `project/src`. Negeer foutmeldingen.
3. Toon alleen de bestanden in `project/src` waarvan de naam met a, b of c begint.
4. Maak van de directory `project` een archief met gzip-compressie en bekijk de inhoud zonder uit te pakken.
5. Pak het archief uit in `/tmp` en vergelijk het aantal bestanden met het origineel.
6. Maak met `dd` een bestand van 50 MB en comprimeer het met gzip, bzip2 en xz. Vergelijk de grootte.
7. Verwijder de directory `project` en alles eronder met één commando.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 5.1](../lab_5-1/README.md) · [← Overzicht](../../README.md) · [Lab 4.2 →](../lab_4-2/README.md)