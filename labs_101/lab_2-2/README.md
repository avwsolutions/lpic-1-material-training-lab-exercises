# Lab 2.2 – Processen starten, sturen en stoppen

| | |
|---|---|
| **Dag** | 1 |
| **Examen** | 101-500 |
| **Hoofdstuk** | H2 Managing Software and Processes |
| **Exam objectives** | 103.5, 103.6 |
| **Duur** | 30 minuten |
| **Werkvorm** | Individueel |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 102–126 |

## Over dit lab

Job control in de shell, prioriteiten met `nice` en `renice`, processen op naam stoppen en een sessie in `tmux` loskoppelen en weer aankoppelen.

## Opdrachten

1. Start `sleep 600` in de achtergrond en `sleep 700` in de voorgrond. Pauzeer de tweede en laat hem in de achtergrond doorlopen.
2. Toon je jobs met hun PID. Haal job 1 naar de voorgrond en breek hem af.
3. Start `sleep 800` in de achtergrond met nice value 10 en controleer de waarde.
4. Zet de nice value op 15. Probeer hem daarna als gewone gebruiker op 5 te zetten. Wat gebeurt er, en waarom?
5. Stop alle sleep-processen met één commando, op naam.
6. Start `top` in een tmux-sessie, koppel de sessie los en koppel hem weer aan. Sorteer in `top` op geheugengebruik.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 2.1](../lab_2-1/README.md) · [← Overzicht](../../README.md) · [Lab 3.1 →](../lab_3-1/README.md)
