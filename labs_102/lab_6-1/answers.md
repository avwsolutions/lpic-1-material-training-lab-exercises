# Uitwerkingen lab 6.1 – De grafische omgeving verkennen

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor Fedora 45 en Ubuntu 26.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Draait je sessie op X11 of op Wayland? Welke waarde heeft `DISPLAY`?

```bash
echo $XDG_SESSION_TYPE        # x11 of wayland
echo $DISPLAY
```

## Opdracht 2

> Welke display manager en welke desktop environment gebruikt je systeem?

```bash
systemctl status display-manager      # bijvoorbeeld gdm
echo $XDG_CURRENT_DESKTOP
```

## Opdracht 3

> Bestaat `/etc/X11/xorg.conf` op je systeem? Wat staat er in `/etc/X11/xorg.conf.d/` of `/usr/share/X11/xorg.conf.d/`?

```bash
ls -l /etc/X11/xorg.conf
ls /etc/X11/xorg.conf.d/ /usr/share/X11/xorg.conf.d/
```
Meestal bestaat `xorg.conf` niet: X.Org detecteert de hardware zelf. De deelbestanden bevatten onder meer de input-instellingen.

## Opdracht 4

> Schakel sticky keys en het on-screen keyboard in via de toegankelijkheidsinstellingen en test ze.

Settings → Universal Access (in nieuwere versies: Accessibility). Schakel Sticky Keys en Screen Keyboard in.

## Opdracht 5

> Log vanaf de ene VM met X11 forwarding in op de andere en start daar een grafisch programma.

```bash
ssh -X gebruiker@andere-vm
xeyes                         # of bijvoorbeeld gedit
```
Op een minimale server moeten `xauth` en een X-programma geïnstalleerd zijn.

## Opdracht 6

> Bekijk `~/.xsession-errors` of het journal van je sessie. Staan er meldingen in?

```bash
cat ~/.xsession-errors
journalctl --user             # op Wayland-sessies
```

---

[← Terug naar lab 6.1](README.md) · [Overzicht](../../README.md)
