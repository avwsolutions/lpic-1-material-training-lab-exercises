# Lab 9.1 – Zelf scripts schrijven

| | |
|---|---|
| **Dag** | 5 |
| **Examen** | 102-500 |
| **Hoofdstuk** | H9 Writing Scripts |
| **Exam objectives** | 105.1, 105.2 |
| **Duur** | 40 minuten |
| **Werkvorm** | Individueel |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 466–500 en p. 514 |

## Over dit lab

Van alias tot script: een blijvende alias, scripts met argumenten en tests, een for-loop over bestanden en commando’s koppelen met `||` voor een foutmelding.

## Voorbereiding

Maak elk script uitvoerbaar met `chmod +x` en start het met `./naam.sh`.

## Opdrachten

1. Voer Exercise 9.1 uit de Study Guide uit (p. 514): een script dat wachtwoordinformatie van systeemgebruikers toont.
2. Maak een alias waarmee je met één woord de vijf grootste bestanden in de huidige directory ziet. Maak hem blijvend.
3. Schrijf een script dat een bestandsnaam als argument krijgt en meldt of het een bestand, een directory of niets is.
4. Breid het script uit: zonder argument toont het een gebruiksmelding en stopt het met exit status 1.
5. Schrijf een script dat alle `.conf`-bestanden in `/etc` afloopt en per bestand het aantal regels toont.
6. Schrijf één regel die een host pingt en bij een fout een melding naar root mailt of naar het log stuurt.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 8.2](../lab_8-2/README.md) · [← Overzicht](../../README.md) · [Lab 9.2 →](../lab_9-2/README.md)