# Lab 7.2 – Logging en tijd

| | |
|---|---|
| **Dag** | 4 |
| **Examen** | 102-500 |
| **Hoofdstuk** | H7 Administering the System |
| **Exam objectives** | 108.1, 108.2 |
| **Duur** | 30 minuten |
| **Werkvorm** | Individueel, met sudo |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 384–416 |

## Over dit lab

Meldingen naar het log sturen met `logger`, een eigen rsyslog-regel, het journal filteren en opschonen, logrotate lezen en de tijdsynchronisatie controleren.

## Opdrachten

1. Stuur met `logger` een melding met facility `local3` en priority `warning`. In welk logbestand komt hij terecht?
2. Voeg een rsyslog-regel toe die alles van `local3` naar `/var/log/cursus.log` schrijft. Herstart de service en test.
3. Toon uit het journal alle meldingen van de SSH-service van vandaag met priority warning of ernstiger.
4. Hoeveel schijfruimte gebruikt het journal? Verwijder alles wat ouder is dan twee dagen.
5. Bekijk een bestand in `/etc/logrotate.d/`. Hoe vaak wordt er geroteerd en hoeveel oude versies blijven bewaard?
6. Is je klok gesynchroniseerd, en met welke daemon? Toon de gebruikte tijdservers.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 7.1](../lab_7-1/README.md) · [← Overzicht](../../README.md) · [Lab 8.1 →](../lab_8-1/README.md)