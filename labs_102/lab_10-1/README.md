# Lab 10.1 – Het systeem doorlichten

| | |
|---|---|
| **Dag** | 5 |
| **Examen** | 102-500 |
| **Hoofdstuk** | H10 Securing Your System |
| **Exam objectives** | 110.1, 110.2 |
| **Duur** | 30 minuten |
| **Werkvorm** | Individueel, met sudo |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 524–553 |

## Over dit lab

Een eerste security-audit: open poorten, overbodige services uitschakelen, wie er inlogt, beperkte sudo-rechten, resource-limieten, SUID-bestanden en logins blokkeren met `/etc/nologin`.

## Voorbereiding

Voor stap 4 en 7 heb je de testgebruiker `tester` nodig. Ruim alles aan het eind op.

## Opdrachten

1. Welke poorten luisteren op je systeem? Vergelijk met een nmap-scan van localhost.
2. Zoek een service die je niet nodig hebt en schakel hem uit, zodat hij ook na een reboot niet start.
3. Wie is er ingelogd? Wanneer was de laatste reboot volgens `last`?
4. Maak een bestand in `/etc/sudoers.d/` waarmee de gebruiker `tester` alleen `systemctl status` mag uitvoeren. Test het.
5. Beperk in de huidige shell het aantal open bestanden tot 20 en probeer wat er dan nog werkt.
6. Maak een lijst van alle SUID-bestanden op het systeem en bewaar hem in je home directory.
7. Maak `/etc/nologin` aan met een onderhoudsmelding en probeer als gewone gebruiker via SSH in te loggen. Ruim op.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 9.2](../lab_9-2/README.md) · [← Overzicht](../../README.md) · [Lab 10.2 →](../lab_10-2/README.md)

ⓒ 2019-2026 Qensus B.V.
