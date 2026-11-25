# Lab 7.1 – Gebruikers en groepen beheren

| | |
|---|---|
| **Dag** | 4 |
| **Examen** | 102-500 |
| **Hoofdstuk** | H7 Administering the System |
| **Exam objectives** | 107.1 |
| **Duur** | 30 minuten |
| **Werkvorm** | Individueel, met sudo |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 354–375 |

## Over dit lab

De levenscyclus van een account: aanmaken vanuit `/etc/skel`, wachtwoord en password aging, groepslidmaatschap, vergrendelen en verwijderen.

## Opdrachten

1. Zet een bestand `welkom.txt` in `/etc/skel`. Maak daarna de gebruiker `tester` aan met home directory en bash als shell.
2. Geef `tester` een wachtwoord en controleer het record in `/etc/passwd` en in `/etc/shadow`.
3. Maak de groep `project` aan en voeg `tester` toe zonder zijn andere groepen te verliezen.
4. Stel in dat het wachtwoord van `tester` na 60 dagen verloopt, met 10 dagen waarschuwing, en dat hij het bij de eerste login moet wijzigen.
5. Vergrendel het account. Wat verandert er in `/etc/shadow`? Ontgrendel het weer.
6. Verwijder `tester` inclusief home directory, en verwijder de groep `project`.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 6.2](../lab_6-2/README.md) · [← Overzicht](../../README.md) · [Lab 7.2 →](../lab_7-2/README.md)

ⓒ 2019-2026 Qensus B.V.
