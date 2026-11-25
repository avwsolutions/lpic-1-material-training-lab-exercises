# LPIC-1 labs

Labopdrachten bij de zesdaagse LPIC-1-training (examens 101-500 en 102-500). De labs volgen de hoofdstukken van de *Sybex LPIC-1 Study Guide, 5e editie* en sluiten aan op de slides van de training.

## Zo werk je met de labs

- De labs voor examen 101-500 staan in [`labs_101/`](labs_101/), die voor examen 102-500 in [`labs_102/`](labs_102/). Elk lab heeft een eigen map, bijvoorbeeld `lab_1-3` voor lab 1.3. Die map bevat een `README.md` met de opdrachten en een `answers.md` met de uitwerkingen.
- Probeer de opdrachten eerst zelf en kijk pas daarna in `answers.md`.
- Labs met de werkvorm *met sudo* vragen beheerrechten. Werk in een VM die je zonder risico kunt aanpassen, en maak vooraf een snapshot.
- Na de labs van een hoofdstuk volgen de 20 review questions aan het eind van dat hoofdstuk in de Study Guide.

## Labomgeving

| VM | Familie | Gebruikt voor |
|---|---|---|
| Fedora 45 | Red Hat | `rpm`, `yum`, Red Hat-configuratiebestanden |
| Ubuntu 26.04 LTS (Server) | Debian | `dpkg`, `apt-get`, Debian-configuratiebestanden, de grafische labs van H6 |

Lab 3.2 vraagt een extra virtuele schijf van 1 GB. Een nieuwere distributieversie werkt meestal ook, maar uitvoer en paden kunnen afwijken.

## Overzicht

| Lab | Dag | Examen | Hoofdstuk | Onderwerp | Duur |
|---|---|---|---|---|---|
| [Lab 1.1](labs_101/lab_1-1/README.md) | 1 | 101-500 | H1 Exploring Linux Command-Line Tools | **Werken op de command line** – Je eerste stappen in de shell: welke shell je gebruikt, het verschil tussen builtins en externe commando’s, variabelen exporteren, PATH aanpassen, de command history en zoeken in de man pages. | 20 minuten |
| [Lab 1.2](labs_101/lab_1-2/README.md) | 1 | 101-500 | H1 Exploring Linux Command-Line Tools | **Tekst filteren uit /etc/passwd** – Tekstfilters combineren op een echt systeembestand: regels selecteren met `head` en `tail`, velden knippen met `cut`, sorteren, tellen, tekens omzetten en een checksum berekenen. | 25 minuten |
| [Lab 1.3](labs_101/lab_1-3/README.md) | 1 | 101-500 | H1 Exploring Linux Command-Line Tools | **Zoeken, omleiden en vervangen** – Zoeken met basic en extended regular expressions, STDOUT en STDERR naar aparte bestanden sturen, tekst vervangen met `sed` en uitvoer tegelijk tonen en opslaan met `tee`. | 30 minuten |
| [Lab 2.1](labs_101/lab_2-1/README.md) | 1 | 101-500 | H2 Managing Software and Processes | **Packages beheren op CentOS en Ubuntu** – Dezelfde taken uitvoeren in de Red Hat- en de Debian-familie: package bij een bestand zoeken, installeren uit repositories, informatie en dependencies opvragen, integriteit controleren en weer verwijderen. | 35 minuten |
| [Lab 2.2](labs_101/lab_2-2/README.md) | 1 | 101-500 | H2 Managing Software and Processes | **Processen starten, sturen en stoppen** – Job control in de shell, prioriteiten met `nice` en `renice`, processen op naam stoppen en een sessie in `tmux` loskoppelen en weer aankoppelen. | 30 minuten |
| [Lab 3.1](labs_101/lab_3-1/README.md) | 2 | 101-500 | H3 Configuring Hardware | **Hardware en modules verkennen** – Hoe de kernel hardware ziet: CPU en geheugen via `/proc`, PCI-apparaten en hun drivers, block devices en het laden en verwijderen van kernel modules. | 20 minuten |
| [Lab 3.2](labs_101/lab_3-2/README.md) | 2 | 101-500 | H3 Configuring Hardware | **Partitioneren, formatteren en mounten** – De volledige route van lege schijf tot bruikbaar filesystem: partitioneren met `fdisk`, ext4 en swap aanmaken, mounten, blijvend vastleggen in `/etc/fstab` en een filesystem controleren. | 35 minuten |
| [Lab 5.1](labs_101/lab_5-1/README.md) | 2 | 101-500 | H5 Booting, Initializing, and Virtualizing Linux | **Booten en services beheren** – Het bootproces van kernelparameters tot boot target, services beheren met `systemctl`, de GRUB-configuratie bekijken, een herstart plannen en eenmalig naar `rescue.target` booten. | 30 minuten |
| [Lab 4.1](labs_101/lab_4-1/README.md) | 2 | 101-500 | H4 Managing Files | **Bestanden beheren en archiveren** – Directories en bestanden aanmaken, kopiëren en verwijderen, werken met wildcards, archieven maken met `tar` en de drie compressietools vergelijken. | 25 minuten |
| [Lab 4.2](labs_101/lab_4-2/README.md) | 2 | 101-500 | H4 Managing Files | **Permissies, links en zoeken** – Permissies in octale notatie, de umask, hard en symbolic links, speciale bits (SGID en sticky bit) en zoeken met `find` op permissies, grootte en tijd. | 30 minuten |
| [Lab 6.1](labs_102/lab_6-1/README.md) | 4 | 102-500 | H6 Configuring the GUI, Localization, and Printing | **De grafische omgeving verkennen** – De bouwstenen van de Linux-desktop: X11 of Wayland, display manager en desktop environment, de X.Org-configuratie, toegankelijkheid en X11 forwarding via SSH. | 20 minuten |
| [Lab 6.2](labs_102/lab_6-2/README.md) | 4 | 102-500 | H6 Configuring the GUI, Localization, and Printing | **Locale, tijdzone en printen** – Lokalisatie in de praktijk: locales en `LC_`-variabelen, tijdzones per commando en voor het hele systeem, character sets omzetten met `iconv`, en de status van CUPS. | 25 minuten |
| [Lab 7.1](labs_102/lab_7-1/README.md) | 4 | 102-500 | H7 Administering the System | **Gebruikers en groepen beheren** – De levenscyclus van een account: aanmaken vanuit `/etc/skel`, wachtwoord en password aging, groepslidmaatschap, vergrendelen en verwijderen. | 30 minuten |
| [Lab 7.2](labs_102/lab_7-2/README.md) | 4 | 102-500 | H7 Administering the System | **Logging en tijd** – Meldingen naar het log sturen met `logger`, een eigen rsyslog-regel, het journal filteren en opschonen, logrotate lezen en de tijdsynchronisatie controleren. | 30 minuten |
| [Lab 8.1](labs_102/lab_8-1/README.md) | 4 | 102-500 | H8 Configuring Basic Networking | **Netwerkconfiguratie bekijken en wijzigen** – De netwerkinstellingen van je eigen systeem uitlezen en wijzigen: adres, prefix, gateway en DNS, subnetten berekenen, tijdelijke adressen met `ip`, NetworkManager-profielen, `/etc/hosts` en de hostnaam. | 30 minuten |
| [Lab 8.2](labs_102/lab_8-2/README.md) | 4 | 102-500 | H8 Configuring Basic Networking | **Netwerkproblemen onderzoeken** – Systematisch troubleshooten: luisterende poorten, poorten op een andere host testen, een verbinding opzetten met netcat, DNS-records opvragen en de volgorde van naamresolutie in `nsswitch.conf`. | 30 minuten |
| [Lab 9.1](labs_102/lab_9-1/README.md) | 5 | 102-500 | H9 Writing Scripts | **Zelf scripts schrijven** – Van alias tot script: een blijvende alias, scripts met argumenten en tests, een for-loop over bestanden en commando’s koppelen met `||` voor een foutmelding. | 40 minuten |
| [Lab 9.2](labs_102/lab_9-2/README.md) | 5 | 102-500 | H9 Writing Scripts | **Taken plannen** – Terugkerende taken met cron, systeembrede cron-bestanden, eenmalige taken met `at` en een blik op systemd timers. | 25 minuten |
| [Lab 10.1](labs_102/lab_10-1/README.md) | 5 | 102-500 | H10 Securing Your System | **Het systeem doorlichten** – Een eerste security-audit: open poorten, overbodige services uitschakelen, wie er inlogt, beperkte sudo-rechten, resource-limieten, SUID-bestanden en logins blokkeren met `/etc/nologin`. | 30 minuten |
| [Lab 10.2](labs_102/lab_10-2/README.md) | 5 | 102-500 | H10 Securing Your System | **SSH keys en GPG** – Inloggen met een SSH key pair, de ssh-agent, host keys in `known_hosts`, en met GPG bestanden versleutelen, ontsleutelen, ondertekenen en verifiëren. | 35 minuten |

Dag 3 en dag 6 zijn examenvoorbereidingsdagen en hebben geen labs. De labs staan in de volgorde van de training; daarom komt H5 op dag 2 vóór H4.

## Mappenstructuur

```text
README.md            ← dit overzicht
labs_101/            ← examen 101-500 (H1–H5)
├── lab_1-1/
│   ├── README.md    ← opdrachten
│   └── answers.md   ← uitwerkingen
├── lab_1-2/
├── …
└── lab_4-2/
labs_102/            ← examen 102-500 (H6–H10)
├── lab_6-1/
├── …
└── lab_10-2/
```

## Bronvermelding & Dankwoord

De structuur, onderwerpen en referentiematerialen in deze repository zijn gebaseerd op de officiële examendoelstellingen en het lesmateriaal van de [Linux Professional Institute (LPI)](https://lpi.org).

* **Exam Objectives:** [LPI Wiki](https://www.lpi.org/our-certifications/exam-101-102-objectives/)
* **Learning Materials:** [LPI Learning Portal](https://www.lpi.org/our-certifications/lpic-1-overview/)
* **License (LPI Learning Materials):** [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)](https://creativecommons.org)

*Disclaimer: "LPIC" en "Linux Professional Institute" zijn geregistreerde handelsmerken van het Linux Professional Institute. Dit is een onafhankelijke, niet-commerciële studiehulp en is niet gelieerd aan, goedgekeurd door of gesponsord door LPI.*
