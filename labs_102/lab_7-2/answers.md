# Uitwerkingen lab 7.2 – Logging en tijd

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Stuur met `logger` een melding met facility `local3` en priority `warning`. In welk logbestand komt hij terecht?

```bash
logger -p local3.warning "Test"
```
CentOS: `/var/log/messages`. Ubuntu: `/var/log/syslog`.

## Opdracht 2

> Voeg een rsyslog-regel toe die alles van `local3` naar `/var/log/cursus.log` schrijft. Herstart de service en test.

Maak `/etc/rsyslog.d/cursus.conf` met deze regel:
```text
local3.*    /var/log/cursus.log
```
Daarna:
```bash
sudo systemctl restart rsyslog
logger -p local3.info "Tweede test"
cat /var/log/cursus.log
```

## Opdracht 3

> Toon uit het journal alle meldingen van de SSH-service van vandaag met priority warning of ernstiger.

```bash
journalctl -u sshd -p warning --since today     # Ubuntu: -u ssh
```

## Opdracht 4

> Hoeveel schijfruimte gebruikt het journal? Verwijder alles wat ouder is dan twee dagen.

```bash
journalctl --disk-usage
sudo journalctl --vacuum-time=2d
```

## Opdracht 5

> Bekijk een bestand in `/etc/logrotate.d/`. Hoe vaak wordt er geroteerd en hoeveel oude versies blijven bewaard?

```bash
cat /etc/logrotate.d/<bestand>
```
Zoek naar `daily`, `weekly` of `monthly`, en naar `rotate` gevolgd door het aantal bewaarde versies.

## Opdracht 6

> Is je klok gesynchroniseerd, en met welke daemon? Toon de gebruikte tijdservers.

```bash
timedatectl
chronyc sources               # CentOS 7: chronyd
```
Ubuntu 18.04 gebruikt standaard `systemd-timesyncd`; `timedatectl` toont of de klok gesynchroniseerd is.

**Extra voor wie klaar is:** staat de hardware clock op UTC? `timedatectl` toont `RTC in local TZ: no`; vergelijk met `sudo hwclock`.

---

[← Terug naar lab 7.2](README.md) · [Overzicht](../../README.md)