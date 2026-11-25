# Lab 1.3 – Zoeken, omleiden en vervangen

| | |
|---|---|
| **Dag** | 1 |
| **Examen** | 101-500 |
| **Hoofdstuk** | H1 Exploring Linux Command-Line Tools |
| **Exam objectives** | 103.4, 103.7 |
| **Duur** | 30 minuten |
| **Werkvorm** | Individueel |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 45–61 |

## Over dit lab

Zoeken met basic en extended regular expressions, STDOUT en STDERR naar aparte bestanden sturen, tekst vervangen met `sed` en uitvoer tegelijk tonen en opslaan met `tee`.

## Opdrachten

1. Toon de accounts in `/etc/passwd` met bash als login shell en tel hoeveel het er zijn.
2. Toon met één extended regex de regels in `/etc/services` die met ssh of telnet beginnen.
3. Zoek als gewone gebruiker alle `.conf`-bestanden onder `/etc`. Bewaar de treffers in `conf.txt` en de foutmeldingen in `fouten.txt`.
4. Toon `/etc/services` zonder commentaarregels en zonder lege regels.
5. Laat `sed` in de uitvoer van `/etc/passwd` elke `/bin/bash` vervangen door `/bin/sh`. Is het bestand zelf gewijzigd?
6. Toon in één pipeline een unieke, gesorteerde lijst van login shells en bewaar die tegelijk in `shells.txt`.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 1.2](../lab_1-2/README.md) · [← Overzicht](../../README.md) · [Lab 2.1 →](../lab_2-1/README.md)

ⓒ 2019-2026 Qensus B.V.
