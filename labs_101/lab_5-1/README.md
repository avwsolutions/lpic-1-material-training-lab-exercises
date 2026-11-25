# Lab 5.1 – Booten en services beheren

| | |
|---|---|
| **Dag** | 2 |
| **Examen** | 101-500 |
| **Hoofdstuk** | H5 Booting, Initializing, and Virtualizing Linux |
| **Exam objectives** | 101.2, 101.3, 102.2 |
| **Duur** | 30 minuten |
| **Werkvorm** | Individueel, met sudo |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 246–286 |

## Over dit lab

Het bootproces van kernelparameters tot boot target, services beheren met `systemctl`, de GRUB-configuratie bekijken, een herstart plannen en eenmalig naar `rescue.target` booten.

## Voorbereiding

Stap 7 vraagt het rootwachtwoord. Op Ubuntu moet dat eerst zijn ingesteld met `sudo passwd root`.

## Opdrachten

1. Met welke parameters is je kernel gestart? Zoek in de bootmeldingen op welke schijven zijn gevonden.
2. Wat is het standaard boot target van je systeem? Welke targets zijn er nog meer?
3. Bekijk de status van de SSH-service. Is hij actief, en start hij automatisch bij het booten?
4. Stop de cron-service, controleer de status en start hem opnieuw.
5. Bekijk `/etc/default/grub`. Welke timeout is ingesteld? Met welk commando genereer je `grub.cfg` opnieuw?
6. Plan een herstart over 15 minuten met een melding, en annuleer hem weer.
7. Herstart de VM, bewerk in het GRUB-menu het eerste item en boot eenmalig naar `rescue.target`.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 3.2](../lab_3-2/README.md) · [← Overzicht](../../README.md) · [Lab 4.1 →](../lab_4-1/README.md)

ⓒ 2019-2026 Qensus B.V.
