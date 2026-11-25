# Lab 9.2 – Taken plannen

| | |
|---|---|
| **Dag** | 5 |
| **Examen** | 102-500 |
| **Hoofdstuk** | H9 Writing Scripts |
| **Exam objectives** | 107.2 |
| **Duur** | 25 minuten |
| **Werkvorm** | Individueel |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 509–515 |

## Over dit lab

Terugkerende taken met cron, systeembrede cron-bestanden, eenmalige taken met `at` en een blik op systemd timers.

## Opdrachten

1. Maak een cron-regel die elke twee minuten de datum toevoegt aan `~/cron.log`. Controleer na een paar minuten.
2. Schrijf de cron-regel voor: elke werkdag om 07:15. En voor: de eerste dag van elke maand om middernacht.
3. Bekijk `/etc/crontab` en de directory `/etc/cron.daily`. Welke taken draaien er dagelijks?
4. Plan met `at` een taak die over drie minuten een bestand in `/tmp` aanmaakt. Bekijk de wachtrij.
5. Plan een tweede at-job voor morgen en verwijder hem weer uit de wachtrij.
6. Welke systemd timers zijn actief? Welke loopt als eerste af?
7. Verwijder je cron-regel en controleer dat je crontab leeg is.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 9.1](../lab_9-1/README.md) · [← Overzicht](../../README.md) · [Lab 10.1 →](../lab_10-1/README.md)

ⓒ 2019-2026 Qensus B.V.
