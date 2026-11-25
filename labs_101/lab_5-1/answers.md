# Uitwerkingen lab 5.1 – Booten en services beheren

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor Fedora 45 en Ubuntu 26.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Met welke parameters is je kernel gestart? Zoek in de bootmeldingen op welke schijven zijn gevonden.

```bash
cat /proc/cmdline
dmesg | grep -i sd
```

## Opdracht 2

> Wat is het standaard boot target van je systeem? Welke targets zijn er nog meer?

```bash
systemctl get-default
systemctl list-units --type=target
```

## Opdracht 3

> Bekijk de status van de SSH-service. Is hij actief, en start hij automatisch bij het booten?

```bash
systemctl status sshd         # Ubuntu: ssh
systemctl is-enabled sshd
```

## Opdracht 4

> Stop de cron-service, controleer de status en start hem opnieuw.

```bash
sudo systemctl stop crond     # Ubuntu: cron
systemctl status crond
sudo systemctl start crond
```

## Opdracht 5

> Bekijk `/etc/default/grub`. Welke timeout is ingesteld? Met welk commando genereer je `grub.cfg` opnieuw?

Zoek de regel `GRUB_TIMEOUT`. Daarna opnieuw genereren:
```bash
sudo grub2-mkconfig -o /boot/grub2/grub.cfg     # CentOS (BIOS)
sudo update-grub                                # Ubuntu
```

## Opdracht 6

> Plan een herstart over 15 minuten met een melding, en annuleer hem weer.

```bash
sudo shutdown -r +15 "Test"
sudo shutdown -c
```

## Opdracht 7

> Herstart de VM, bewerk in het GRUB-menu het eerste item en boot eenmalig naar `rescue.target`.

1. Druk tijdens het booten op Shift of Esc voor het GRUB-menu.
2. Kies het eerste item en druk op `e`.
3. Zet achter de `linux`-regel: `systemd.unit=rescue.target`
4. Boot met Ctrl+X.

Het rootwachtwoord is nodig; de wijziging geldt alleen voor deze ene boot.

---

[← Terug naar lab 5.1](README.md) · [Overzicht](../../README.md)
