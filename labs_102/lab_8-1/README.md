# Lab 8.1 – Netwerkconfiguratie bekijken en wijzigen

| | |
|---|---|
| **Dag** | 4 |
| **Examen** | 102-500 |
| **Hoofdstuk** | H8 Configuring Basic Networking |
| **Exam objectives** | 109.1, 109.2 |
| **Duur** | 30 minuten |
| **Werkvorm** | Individueel, met sudo |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 426–445 |

## Over dit lab

De netwerkinstellingen van je eigen systeem uitlezen en wijzigen: adres, prefix, gateway en DNS, subnetten berekenen, tijdelijke adressen met `ip`, NetworkManager-profielen, `/etc/hosts` en de hostnaam.

## Opdrachten

1. Wat zijn je IP-adres, prefix, default gateway en DNS-server? Gebruik alleen iproute2 en de configuratiebestanden.
2. Bereken het netwerkadres, het broadcastadres en het aantal hosts van jouw subnet.
3. Voeg tijdelijk een tweede adres `10.99.0.1/24` toe aan je interface, controleer het en verwijder het weer.
4. Toon de verbindingsprofielen van NetworkManager. Welk profiel is actief op welk device?
5. Voeg aan `/etc/hosts` een regel toe zodat de naam `buur` naar de VM van je buur wijst, en test met `ping`.
6. Wijzig je hostnaam blijvend naar `lpic` plus je initialen en controleer het resultaat.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 7.2](../lab_7-2/README.md) · [← Overzicht](../../README.md) · [Lab 8.2 →](../lab_8-2/README.md)

ⓒ 2019-2026 Qensus B.V.
