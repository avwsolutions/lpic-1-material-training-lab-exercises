# Uitwerkingen lab 1.2 – Tekst filteren uit /etc/passwd

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor Fedora 45 en Ubuntu 26.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Toon de eerste vijf en daarna de laatste drie regels van `/etc/passwd`.

```bash
head -n 5 /etc/passwd
tail -n 3 /etc/passwd
```

## Opdracht 2

> Maak een lijst van alle gebruikersnamen met hun login shell.

```bash
cut -d: -f1,7 /etc/passwd
```

## Opdracht 3

> Tel hoe vaak elke login shell voorkomt, de meest gebruikte bovenaan.

```bash
cut -d: -f7 /etc/passwd | sort | uniq -c | sort -nr
```
`uniq` vergelijkt alleen opeenvolgende regels; daarom eerst sorteren.

## Opdracht 4

> Sorteer het bestand numeriek op UID en zet regelnummers voor de uitvoer.

```bash
sort -t: -k3 -n /etc/passwd | nl
```

## Opdracht 5

> Zet de lijst met gebruikersnamen om naar hoofdletters.

```bash
cut -d: -f1 /etc/passwd | tr 'a-z' 'A-Z'
```

## Opdracht 6

> Bereken de SHA-256-checksum van `/etc/passwd` en vergelijk hem met die van je buur. Verklaar het verschil.

```bash
sha256sum /etc/passwd
```
Elk verschil in inhoud, hoe klein ook (een extra account, een andere shell), geeft een totaal andere hash.

---

[← Terug naar lab 1.2](README.md) · [Overzicht](../../README.md)
