# Uitwerkingen lab 2.2 – Processen starten, sturen en stoppen

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor Fedora 45 en Ubuntu 26.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Start `sleep 600` in de achtergrond en `sleep 700` in de voorgrond. Pauzeer de tweede en laat hem in de achtergrond doorlopen.

```bash
sleep 600 &
sleep 700
# Ctrl+Z pauzeert sleep 700
bg
```

## Opdracht 2

> Toon je jobs met hun PID. Haal job 1 naar de voorgrond en breek hem af.

```bash
jobs -l
fg %1
# Ctrl+C breekt de job af
```

## Opdracht 3

> Start `sleep 800` in de achtergrond met nice value 10 en controleer de waarde.

```bash
nice -n 10 sleep 800 &
ps -l                         # kolom NI
```

## Opdracht 4

> Zet de nice value op 15. Probeer hem daarna als gewone gebruiker op 5 te zetten. Wat gebeurt er, en waarom?

```bash
renice -n 15 -p <PID>         # lukt
renice -n 5 -p <PID>          # Permission denied
```
Een gewone gebruiker mag de nice value alleen verhogen (de prioriteit verlagen). Verlagen mag alleen root.

## Opdracht 5

> Stop alle sleep-processen met één commando, op naam.

```bash
killall sleep                 # of: pkill sleep
```

## Opdracht 6

> Start `top` in een tmux-sessie, koppel de sessie los en koppel hem weer aan. Sorteer in `top` op geheugengebruik.

```bash
tmux
top
# Ctrl+B, daarna d: sessie loskoppelen
tmux attach
# in top: Shift+M sorteert op geheugengebruik
```
Is `tmux` niet geïnstalleerd, installeer het dan (herhaling van lab 2.1) of gebruik `screen`.

---

[← Terug naar lab 2.2](README.md) · [Overzicht](../../README.md)
