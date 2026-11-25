# Lab 3.2 – Partitioneren, formatteren en mounten

| | |
|---|---|
| **Dag** | 2 |
| **Examen** | 101-500 |
| **Hoofdstuk** | H3 Configuring Hardware |
| **Exam objectives** | 104.1, 104.2, 104.3 |
| **Duur** | 35 minuten |
| **Werkvorm** | Individueel, met sudo |
| **Naslag** | Sybex LPIC-1 Study Guide, 5e editie, p. 158–174 |

## Over dit lab

De volledige route van lege schijf tot bruikbaar filesystem: partitioneren met `fdisk`, ext4 en swap aanmaken, mounten, blijvend vastleggen in `/etc/fstab` en een filesystem controleren.

## Voorbereiding

Voeg vooraf een extra virtuele schijf van 1 GB toe aan je VM. Werk uitsluitend op die extra schijf.

## Opdrachten

1. Zoek de extra schijf van 1 GB op. Welke devicenaam heeft hij?
2. Maak met `fdisk` twee partities: 600 MB type Linux en de rest type Linux swap.
3. Maak een ext4-filesystem op de eerste partitie en geef het het label `data`.
4. Mount het filesystem op `/mnt/data` en controleer de vrije ruimte en het aantal vrije inodes.
5. Richt de tweede partitie in als swap, activeer hem en controleer het resultaat.
6. Zoek de UUID op en voeg een regel aan `/etc/fstab` toe. Test met `umount` gevolgd door `mount -a`.
7. Unmount het filesystem en voer een geforceerde controle uit.

## Antwoorden

Probeer de opdrachten eerst zelf. De uitwerkingen staan in [answers.md](answers.md).

---

[← Lab 3.1](../lab_3-1/README.md) · [← Overzicht](../../README.md) · [Lab 5.1 →](../lab_5-1/README.md)