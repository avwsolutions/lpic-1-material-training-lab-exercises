# Uitwerkingen lab 3.2 – Partitioneren, formatteren en mounten

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor CentOS 7 en Ubuntu 18.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Zoek de extra schijf van 1 GB op. Welke devicenaam heeft hij?

```bash
lsblk
```
Meestal is dit `/dev/sdb`. Controleer het goed voordat je verdergaat.

## Opdracht 2

> Maak met `fdisk` twee partities: 600 MB type Linux en de rest type Linux swap.

```text
sudo fdisk /dev/sdb
n, p, 1, Enter, +600M         # eerste partitie
n, p, 2, Enter, Enter         # tweede partitie, rest van de schijf
t, 2, 82                      # type van partitie 2: Linux swap
w                             # wegschrijven
```

## Opdracht 3

> Maak een ext4-filesystem op de eerste partitie en geef het het label `data`.

```bash
sudo mkfs -t ext4 -L data /dev/sdb1
```

## Opdracht 4

> Mount het filesystem op `/mnt/data` en controleer de vrije ruimte en het aantal vrije inodes.

```bash
sudo mkdir /mnt/data
sudo mount /dev/sdb1 /mnt/data
df -h /mnt/data
df -i /mnt/data
```

## Opdracht 5

> Richt de tweede partitie in als swap, activeer hem en controleer het resultaat.

```bash
sudo mkswap /dev/sdb2
sudo swapon /dev/sdb2
swapon -s                     # of: free -h
```

## Opdracht 6

> Zoek de UUID op en voeg een regel aan `/etc/fstab` toe. Test met `umount` gevolgd door `mount -a`.

```bash
sudo blkid /dev/sdb1
```
Regel in `/etc/fstab`:
```text
UUID=<uuid>  /mnt/data  ext4  defaults  0  2
```
Test:
```bash
sudo umount /mnt/data
sudo mount -a
df -h /mnt/data
```

## Opdracht 7

> Unmount het filesystem en voer een geforceerde controle uit.

```bash
sudo umount /mnt/data
sudo e2fsck -f /dev/sdb1
```
Geen extra schijf beschikbaar? Gebruik dan een loop device op een bestand.

---

[← Terug naar lab 3.2](README.md) · [Overzicht](../../README.md)