# Lab 8.2 – Netwerkproblemen onderzoeken

| | |
|---|---|
| **Dag** | 4 |
| **Examen** | 102-500 |
| **Hoofdstuk** | H8 Configuring Basic Networking |
| **Exam objectives** | 109.3, 109.4 |
| **Duur** | 30 minuten |
| **Werkvorm** | In tweetallen |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 447–457 |

## Over dit lab

Systematisch troubleshooten: luisterende poorten, poorten op een andere host testen, een verbinding opzetten met netcat, DNS-records opvragen en de volgorde van naamresolutie in `nsswitch.conf`.

## Voorbereiding

Maak een kopie van `/etc/nsswitch.conf` voordat je aan stap 6 begint.

## Opdrachten

1. Voer Exercise 8.1 uit de Study Guide uit (p. 457): breng je netwerkomgeving in kaart.
2. Welke TCP-poorten luisteren op je systeem, en welk proces hoort bij poort 22?
3. Test vanaf jouw VM of poort 22 en poort 80 op de VM van je partner open zijn.
4. Zet met netcat een luisteraar op poort 5000 en laat je partner er een tekstregel naartoe sturen.
5. Zoek de MX-records van een domein naar keuze op en doe een reverse lookup van één van de gevonden adressen.
6. Zet in `nsswitch.conf` bij `hosts` de volgorde op `dns files`. Wat geeft `getent hosts buur` nu, en waarom? Zet het terug.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 8.1](../lab_8-1/README.md) · [← Overzicht](../../README.md) · [Lab 9.1 →](../lab_9-1/README.md)

ⓒ 2019-2026 Qensus B.V.
