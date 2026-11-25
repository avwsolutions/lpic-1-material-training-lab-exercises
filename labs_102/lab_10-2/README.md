# Lab 10.2 – SSH keys en GPG

| | |
|---|---|
| **Dag** | 5 |
| **Examen** | 102-500 |
| **Hoofdstuk** | H10 Securing Your System |
| **Exam objectives** | 110.3 |
| **Duur** | 35 minuten |
| **Werkvorm** | In tweetallen |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 555–574 |

## Over dit lab

Inloggen met een SSH key pair, de ssh-agent, host keys in `known_hosts`, en met GPG bestanden versleutelen, ontsleutelen, ondertekenen en verifiëren.

## Voorbereiding

Het aanmaken van een GPG-key kan op een VM lang duren door gebrek aan entropie.

## Opdrachten

1. Maak een SSH key pair met een passphrase. Welke bestanden zijn er aangemaakt, met welke permissies?
2. Installeer je public key op de VM van je partner en log in zonder accountwachtwoord. Wat staat er in `authorized_keys`?
3. Start een ssh-agent, voeg je key toe en log opnieuw in. Wat is het verschil?
4. Zoek in `known_hosts` de regel voor de VM van je partner. Wat gebeurt er als je die regel verwijdert?
5. Maak een GPG key pair, exporteer je public key en wissel hem uit met je partner.
6. Versleutel een tekstbestand voor je partner en laat het ontsleutelen. Probeer het ook zelf te ontsleutelen.
7. Onderteken een bestand met een detached signature. Laat je partner de signature controleren, ook na een wijziging in het bestand.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 10.1](../lab_10-1/README.md) · [← Overzicht](../../README.md)