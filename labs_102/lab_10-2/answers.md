# Uitwerkingen lab 10.2 – SSH keys en GPG

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Maak een SSH key pair met een passphrase. Welke bestanden zijn er aangemaakt, met welke permissies?

```bash
ssh-keygen -t rsa -b 4096
ls -l ~/.ssh
```
`id_rsa` (600) is de private key, `id_rsa.pub` (644) de public key.

## Opdracht 2

> Installeer je public key op de VM van je partner en log in zonder accountwachtwoord. Wat staat er in `authorized_keys`?

```bash
ssh-copy-id gebruiker@partner
ssh gebruiker@partner         # vraagt nu de passphrase van de key
cat ~/.ssh/authorized_keys    # op de VM van je partner
```
In `authorized_keys` staat jouw public key, één key per regel.

## Opdracht 3

> Start een ssh-agent, voeg je key toe en log opnieuw in. Wat is het verschil?

```bash
ssh-agent bash
ssh-add
ssh gebruiker@partner
```
Inloggen gaat nu zonder passphrase: de agent houdt de ontgrendelde key vast.

## Opdracht 4

> Zoek in `known_hosts` de regel voor de VM van je partner. Wat gebeurt er als je die regel verwijdert?

```bash
ssh-keygen -R <hostnaam>
```
Bij de volgende verbinding moet je de host key opnieuw accepteren.

## Opdracht 5

> Maak een GPG key pair, exporteer je public key en wissel hem uit met je partner.

```bash
gpg --gen-key
gpg --export -a <naam> > naam.asc
scp naam.asc gebruiker@partner:
gpg --import partner.asc      # de key van je partner
```

## Opdracht 6

> Versleutel een tekstbestand voor je partner en laat het ontsleutelen. Probeer het ook zelf te ontsleutelen.

```bash
gpg -e -r <partner> bestand.txt
gpg -d bestand.txt.gpg        # door je partner
```
Zelf ontsleutelen lukt niet: daarvoor is de private key van je partner nodig.

## Opdracht 7

> Onderteken een bestand met een detached signature. Laat je partner de signature controleren, ook na een wijziging in het bestand.

```bash
gpg --detach-sign bestand.txt
gpg --verify bestand.txt.sig bestand.txt     # door je partner
```
Je partner heeft zowel het bestand als de `.sig` nodig. Na een wijziging in het bestand meldt `gpg` een `BAD signature`.

---

[← Terug naar lab 10.2](README.md) · [Overzicht](../../README.md)

ⓒ 2019-2026 Qensus B.V.
