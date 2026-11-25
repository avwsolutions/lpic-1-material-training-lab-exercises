# Uitwerkingen lab 9.2 – Taken plannen

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Maak een cron-regel die elke twee minuten de datum toevoegt aan `~/cron.log`. Controleer na een paar minuten.

```bash
crontab -e
```
Regel:
```text
*/2 * * * * date >> ~/cron.log
```

## Opdracht 2

> Schrijf de cron-regel voor: elke werkdag om 07:15. En voor: de eerste dag van elke maand om middernacht.

```text
15 7 * * 1-5  commando        # elke werkdag om 07:15
0 0 1 * *     commando        # eerste dag van de maand, middernacht
```

## Opdracht 3

> Bekijk `/etc/crontab` en de directory `/etc/cron.daily`. Welke taken draaien er dagelijks?

```bash
cat /etc/crontab
ls /etc/cron.daily
```
Bijvoorbeeld `logrotate` en `man-db`.

## Opdracht 4

> Plan met `at` een taak die over drie minuten een bestand in `/tmp` aanmaakt. Bekijk de wachtrij.

```bash
at now + 3 minutes
at> touch /tmp/at-test
at> <Ctrl+D>
atq
```
Is `at` niet aanwezig, installeer dan het package `at` en start de service `atd`.

## Opdracht 5

> Plan een tweede at-job voor morgen en verwijder hem weer uit de wachtrij.

```bash
at tomorrow
at> echo test
at> <Ctrl+D>
atq
atrm <jobnummer>
```

## Opdracht 6

> Welke systemd timers zijn actief? Welke loopt als eerste af?

```bash
systemctl list-timers
```

## Opdracht 7

> Verwijder je cron-regel en controleer dat je crontab leeg is.

```bash
crontab -e                    # wis de regel; of: crontab -r
crontab -l
```

---

[← Terug naar lab 9.2](README.md) · [Overzicht](../../README.md)

ⓒ 2019-2026 Qensus B.V.
