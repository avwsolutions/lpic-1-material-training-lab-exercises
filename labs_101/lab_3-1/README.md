# Lab 3.1 – Hardware en modules verkennen

| | |
|---|---|
| **Dag** | 2 |
| **Examen** | 101-500 |
| **Hoofdstuk** | H3 Configuring Hardware |
| **Exam objectives** | 101.1 |
| **Duur** | 20 minuten |
| **Werkvorm** | Individueel |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 134–154 |

## Over dit lab

Hoe de kernel hardware ziet: CPU en geheugen via `/proc`, PCI-apparaten en hun drivers, block devices en het laden en verwijderen van kernel modules.

## Opdrachten

1. Hoeveel CPU-cores en hoeveel geheugen ziet de kernel? Gebruik alleen bestanden onder `/proc`.
2. Toon de PCI-apparaten en zoek uit welke kernel driver de netwerkkaart gebruikt.
3. Toon de block devices. Welke schijven en partities heeft je systeem?
4. Hoeveel modules zijn er geladen? Zoek van één module de beschrijving en de bestandslocatie op.
5. Laad de module `dummy`, controleer dat hij geladen is en verwijder hem weer.
6. In welke directory staan de modules van je draaiende kernel?

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 2.2](../lab_2-2/README.md) · [← Overzicht](../../README.md) · [Lab 3.2 →](../lab_3-2/README.md)