# Lab 6.1 – De grafische omgeving verkennen

| | |
|---|---|
| **Dag** | 4 |
| **Examen** | 102-500 |
| **Hoofdstuk** | H6 Configuring the GUI, Localization, and Printing |
| **Exam objectives** | 106.1, 106.2, 106.3 |
| **Duur** | 20 minuten |
| **Werkvorm** | Individueel, op de desktop-VM |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 306–328 |

## Over dit lab

De bouwstenen van de Linux-desktop: X11 of Wayland, display manager en desktop environment, de X.Org-configuratie, toegankelijkheid en X11 forwarding via SSH.

## Voorbereiding

Gebruik de Ubuntu Desktop-VM. Voor stap 5 heb je een tweede VM nodig met `xauth` en een grafisch programma.

## Opdrachten

1. Draait je sessie op X11 of op Wayland? Welke waarde heeft `DISPLAY`?
2. Welke display manager en welke desktop environment gebruikt je systeem?
3. Bestaat `/etc/X11/xorg.conf` op je systeem? Wat staat er in `/etc/X11/xorg.conf.d/` of `/usr/share/X11/xorg.conf.d/`?
4. Schakel sticky keys en het on-screen keyboard in via de toegankelijkheidsinstellingen en test ze.
5. Log vanaf de ene VM met X11 forwarding in op de andere en start daar een grafisch programma.
6. Bekijk `~/.xsession-errors` of het journal van je sessie. Staan er meldingen in?

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 4.2](../../labs_101/lab_4-2/README.md) · [← Overzicht](../../README.md) · [Lab 6.2 →](../lab_6-2/README.md)

ⓒ 2019-2026 Qensus B.V.
