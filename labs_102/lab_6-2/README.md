# Lab 6.2 – Locale, tijdzone en printen

| | |
|---|---|
| **Dag** | 4 |
| **Examen** | 102-500 |
| **Hoofdstuk** | H6 Configuring the GUI, Localization, and Printing |
| **Exam objectives** | 107.3, 108.4 |
| **Duur** | 25 minuten |
| **Werkvorm** | Individueel, met sudo |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 333–345 |

## Over dit lab

Lokalisatie in de praktijk: locales en `LC_`-variabelen, tijdzones per commando en voor het hele systeem, character sets omzetten met `iconv`, en de status van CUPS.

## Opdrachten

1. Toon je huidige locale. Welke locales zijn er op je systeem beschikbaar?
2. Voer `date` uit met `LC_TIME` ingesteld op een andere beschikbare locale en daarna met `LC_ALL=C`. Wat verschilt?
3. Toon de huidige tijd in Tokyo zonder de systeemtijdzone te wijzigen.
4. Wijzig de systeemtijdzone naar `America/New_York`, controleer `/etc/localtime` en zet hem terug.
5. Maak een bestand in ISO-8859-1 met een woord met accenten en zet het om naar UTF-8. Controleer met `file`.
6. Draait CUPS? Bekijk de printers en queues vanaf de command line en open de webinterface.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 6.1](../lab_6-1/README.md) · [← Overzicht](../../README.md) · [Lab 7.1 →](../lab_7-1/README.md)