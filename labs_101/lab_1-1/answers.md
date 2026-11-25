# Uitwerkingen lab 1.1 – Werken op de command line

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Bepaal welke shell je gebruikt en waar `/bin/sh` naar verwijst.

```bash
echo $SHELL
readlink /bin/sh        # of: ls -l /bin/sh
```
Op CentOS wijst `/bin/sh` naar `bash`, op Ubuntu naar `dash`.

## Opdracht 2

> Zoek uit of `cd`, `ls` en `pwd` een builtin of een extern programma zijn.

```bash
type cd ls pwd
```
`cd` en `pwd` zijn shell builtins; `ls` is een extern programma, vaak met een alias erbovenop. `type -a pwd` laat zien dat er naast de builtin ook een extern programma bestaat.

## Opdracht 3

> Maak een variabele `CURSUS` met de waarde `LPIC-1`. Start een subshell: bestaat hij daar? Exporteer hem en controleer opnieuw.

```bash
CURSUS=LPIC-1
bash                    # start een subshell
echo $CURSUS            # leeg: een lokale variabele wordt niet geërfd
exit
export CURSUS
bash
echo $CURSUS            # LPIC-1
exit
```

## Opdracht 4

> Voeg de directory `~/bin` tijdelijk toe aan je `PATH` en toon het resultaat.

```bash
PATH=$PATH:~/bin
echo $PATH
```
De wijziging geldt alleen voor de huidige shell.

## Opdracht 5

> Voer via de history het commando uit stap 1 opnieuw uit, zonder het over te typen.

```bash
history                 # zoek het nummer van het commando op
!12                     # voer commando 12 opnieuw uit
```
Of druk op Ctrl+R en typ een deel van het commando.

## Opdracht 6

> Zoek met `man -k` het commando dat kernelinformatie toont. Welke optie geeft alleen de kernel release?

```bash
man -k kernel           # of: apropos kernel
uname -r                # alleen de kernel release
```
De zoekresultaten leiden naar `uname`.

---

[← Terug naar lab 1.1](README.md) · [Overzicht](../../README.md)
