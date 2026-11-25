# Uitwerkingen lab 9.1 – Zelf scripts schrijven

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Voer Exercise 9.1 uit de Study Guide uit (p. 514): een script dat wachtwoordinformatie van systeemgebruikers toont.

Volg de stappen van Exercise 9.1 in de Study Guide (p. 514); het script staat daar volledig uitgewerkt.

## Opdracht 2

> Maak een alias waarmee je met één woord de vijf grootste bestanden in de huidige directory ziet. Maak hem blijvend.

Zet in `~/.bashrc`:
```bash
alias groot='ls -lS | head -6'
```
Daarna:
```bash
source ~/.bashrc
groot
```

## Opdracht 3

> Schrijf een script dat een bestandsnaam als argument krijgt en meldt of het een bestand, een directory of niets is.

```bash
#!/bin/bash
if [ -f "$1" ]; then
  echo "bestand"
elif [ -d "$1" ]; then
  echo "directory"
else
  echo "bestaat niet"
fi
```

## Opdracht 4

> Breid het script uit: zonder argument toont het een gebruiksmelding en stopt het met exit status 1.

Zet bovenaan het script, na de shebang:
```bash
if [ $# -eq 0 ]; then
  echo "Gebruik: $0 naam"
  exit 1
fi
```

## Opdracht 5

> Schrijf een script dat alle `.conf`-bestanden in `/etc` afloopt en per bestand het aantal regels toont.

```bash
#!/bin/bash
for f in /etc/*.conf; do
  echo "$f: $(wc -l < "$f")"
done
```

## Opdracht 6

> Schrijf één regel die een host pingt en bij een fout een melding naar root mailt of naar het log stuurt.

```bash
ping -c1 <host> > /dev/null || logger "<host> onbereikbaar"
ping -c1 <host> > /dev/null || echo "<host> onbereikbaar" | mail -s "Ping mislukt" root
```

---

[← Terug naar lab 9.1](README.md) · [Overzicht](../../README.md)

ⓒ 2019-2026 Qensus B.V.
