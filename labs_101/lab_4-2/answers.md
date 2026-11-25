# Uitwerkingen lab 4.2 – Permissies, links en zoeken

> De opdrachten staan in [README.md](README.md). De uitwerkingen zijn geschreven voor Fedora 45 en Ubuntu 26.04 LTS; uitvoer en paden kunnen per distributie en versie verschillen.

## Opdracht 1

> Maak een bestand `geheim.txt` dat alleen jij kunt lezen en schrijven. Gebruik de octale notatie.

```bash
touch geheim.txt
chmod 600 geheim.txt
```

## Opdracht 2

> Stel je umask zo in dat nieuwe bestanden `rw-r-----` krijgen. Controleer met een nieuw bestand en een nieuwe directory.

```bash
umask 027
touch t1
mkdir d1
ls -ld t1 d1                  # 640 en 750
```

## Opdracht 3

> Maak een hard link en een symbolic link naar `geheim.txt`. Vergelijk de inodes en de link count.

```bash
ln geheim.txt hard
ln -s geheim.txt zacht
ls -li geheim.txt hard zacht
```
`hard` heeft dezelfde inode als `geheim.txt` en de link count is 2; `zacht` heeft een eigen inode.

## Opdracht 4

> Verwijder `geheim.txt`. Welke link werkt nog, en waarom?

```bash
rm geheim.txt
cat hard                      # werkt
cat zacht                     # No such file or directory
```
De hard link werkt nog: de inode en de data blijven bestaan zolang er een naam naar wijst. De symbolic link wijst naar een naam die niet meer bestaat en is verbroken.

## Opdracht 5

> Maak een directory `gedeeld` waarin nieuwe bestanden de groep erven en alleen de eigenaar zijn bestanden mag verwijderen.

```bash
mkdir gedeeld
chmod 3775 gedeeld            # of: chmod g+s,o+t gedeeld
ls -ld gedeeld
```

## Opdracht 6

> Zoek alle bestanden met het SUID-bit onder `/usr/bin`.

```bash
find /usr/bin -perm -4000
```

## Opdracht 7

> Zoek onder `/var/log` de bestanden groter dan 1 MB die de afgelopen twee dagen zijn gewijzigd.

```bash
sudo find /var/log -type f -size +1M -mtime -2
```

---

[← Terug naar lab 4.2](README.md) · [Overzicht](../../README.md)