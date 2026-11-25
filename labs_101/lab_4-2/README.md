# Lab 4.2 – Permissies, links en zoeken

| | |
|---|---|
| **Dag** | 2 |
| **Examen** | 101-500 |
| **Hoofdstuk** | H4 Managing Files |
| **Exam objectives** | 104.5, 104.6, 104.7 |
| **Duur** | 30 minuten |
| **Werkvorm** | Individueel |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 213–239 |

## Over dit lab

Permissies in octale notatie, de umask, hard en symbolic links, speciale bits (SGID en sticky bit) en zoeken met `find` op permissies, grootte en tijd.

## Opdrachten

1. Maak een bestand `geheim.txt` dat alleen jij kunt lezen en schrijven. Gebruik de octale notatie.
2. Stel je umask zo in dat nieuwe bestanden `rw-r-----` krijgen. Controleer met een nieuw bestand en een nieuwe directory.
3. Maak een hard link en een symbolic link naar `geheim.txt`. Vergelijk de inodes en de link count.
4. Verwijder `geheim.txt`. Welke link werkt nog, en waarom?
5. Maak een directory `gedeeld` waarin nieuwe bestanden de groep erven en alleen de eigenaar zijn bestanden mag verwijderen.
6. Zoek alle bestanden met het SUID-bit onder `/usr/bin`.
7. Zoek onder `/var/log` de bestanden groter dan 1 MB die de afgelopen twee dagen zijn gewijzigd.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 4.1](../lab_4-1/README.md) · [← Overzicht](../../README.md) · [Lab 6.1 →](../../labs_102/lab_6-1/README.md)

ⓒ 2019-2026 Qensus B.V.
