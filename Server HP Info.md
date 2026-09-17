# Server HP - informazioni hardware e software

Informazioni rilevate con:

```text
sudo inxi -Fxxxa
```

## Sistema

- Host: `[REDACTED_HOST]` (prompt: `user@host:~$`)
- Distribuzione: Debian GNU/Linux 13 (trixie)
- Kernel: `6.12.107+deb13-amd64`
- Architettura: `x86_64`, 64 bit
- Compilatore kernel: GCC `14.2.0`
- Clocksource: `tsc`; disponibili: `acpi_pm`
- Parametri di avvio: `[REDACTED_BOOT_PARAMETERS]`
- Console: `pty pts/2`
- Init: `systemd` versione `257`
- Shell: Bash versione `5.2.37`
- Versione `inxi`: `3.3.38`
- Uptime: 1 giorno e 46 minuti
- Processi: 198

## Computer e firmware

- Tipo: sistema rimovibile (`Detachable System`)
- Produttore: HP
- Prodotto: HP x2 Detachable 10-p0XX
- Versione prodotto: `N/A`
- Scheda madre: HP `827C`, versione `93.23`
- Numero di serie sistema: `[REDACTED]`
- Chassis: tipo `32`, seriale `N/A`
- Numero di serie scheda madre: `[REDACTED]`
- Codice parte: `[REDACTED]`
- UUID scheda madre: `[REDACTED]`
- UEFI: American Megatrends `F.21`, del 10 maggio 2017

## Batteria

- Identificativo: `BATC`
- Carica: `25.2 Wh` (100%)
- Capacita attuale massima: `25.2 Wh`
- Capacita di progetto: `32.6 Wh`
- Stato capacita: 77.3% (usura stimata 22.7%)
- Tensione: `8.6 V`; minima: `7.7 V`
- Modello: `Intel SR 1 SR Real Battery`
- Tecnologia: agli ioni di litio (`Li-ion`)
- Numero di serie: `[REDACTED]`
- Stato: completamente carica (`full`)

## Processore

- Modello: Intel Atom x5-Z8350
- Socket: `BGA1155`; tipo: MCP
- Architettura: Airmont, livello `v2`
- Core: 4; cluster: 2; die: 1; SMT: non supportato
- Processo: Intel 14 nm; produzione: 2015-2017
- Famiglia: `6`; model ID: `0x4C (76)`; stepping: `4`
- Microcodice: `0x411`
- Cache L1: 224 KiB (dati 4x24 KiB, istruzioni 4x32 KiB)
- Cache L2: 2 MiB (2x1024 KiB)
- Frequenza media/minima/massima: 480/480/1920 MHz
- Frequenza base/boost dichiarata: 1440/2400 MHz
- Driver scaling: `intel_cpufreq`
- Governor: `schedutil`
- Tensione: 1.2 V; clock esterno: 80 MHz
- BogoMIPS: 11520
- Frequenza dei core durante la rilevazione: core 1-4 a 480 MHz
- Funzionalita: `ht`, `lm`, `nx`, `pae`, `sse`, `sse2`, `sse3`, `sse4_1`, `sse4_2`, `ssse3`, `vmx`

### Vulnerabilita e mitigazioni CPU

- Non interessato: Gather Data Sampling, Indirect Target Selection, iTLB Multihit, L1TF, Register File Data Sampling, Retbleed, Speculative Return Stack Overflow, Speculative Store Bypass, SRBDS, TSA, TSX Async Abort, VMSCAPE.
- MDS: pulizia dei buffer CPU; SMT disabilitato.
- Meltdown: PTI.
- MMIO Stale Data: stato sconosciuto, nessuna mitigazione.
- Spectre v1: barriere usercopy/swapgs e sanitizzazione dei puntatori `__user`.
- Spectre v2: Retpolines, IBPB condizionale, IBRS_FW e RSB filling; STIBP disabilitato; PBRSB-eIBRS e BHI non interessati.

## Grafica, display e videocamera

### GPU

- Dispositivo: Intel Atom/Celeron/Pentium x5-E8000/J3xxx/N3xxx Integrated Graphics
- Vendor: Hewlett-Packard
- Driver: `i915` (kernel)
- Architettura: Gen-8; processo: Intel 14 nm
- Bus PCI: `00:02.0`; chip ID: `8086:22b0`; classe: `0300`
- Uscita attiva: `eDP-1`; uscite vuote: `DP-1`, `HDMI-A-1`
- Renderer: Mesa Intel HD Graphics (CHV); software disponibile: `llvmpipe` LLVM 19.1.7 (128 bit)

### Display e API

- Server grafico: nessun dato; console TTY `118x76`, modalita headless rilevata
- Monitor: BOE Display `0x03f2`, collegato a `eDP-1`, costruito nel 2015
- Risoluzione: `1280x800`, rapporto 16:10, unica modalita
- Densita: 150 DPI; gamma: 1.2
- Dimensioni: 217 x 136 mm (8.54 x 5.35 pollici); diagonale 256 mm (10.1 pollici)
- EGL: `1.5`; driver `crocus`, `swrast`; piattaforme `gbm`, `surfaceless`, `device`
- OpenGL: `4.6` compatibile `4.5`; Mesa `25.0.7-2+deb13u1`
- Wayland e X11: inattivi; dati OpenGL dalla console tramite EGL
- Strumenti: `eglinfo`, `glxinfo`, `xdriinfo`, `xdpyinfo`, `xprop`, `xrandr`

### Videocamera

- Cheng Uei Precision Industry (Foxlink) HP TrueVision HD
- Driver: `uvcvideo`; USB 2.0, 480 Mb/s, 1 lane, modalita 2.0
- Bus: `1-4.2:5`; chip ID: `05c8:03a3`; classe: `0e02`
- Numero di serie: `[REDACTED]`

## Audio

- Dispositivo: Intel Atom/Celeron/Pentium x5-E8000/J3xxx/N3xxx Series Imaging Unit
- Vendor: Hewlett-Packard
- Driver: `intel_atomisp2_pm`, versione kernel
- API: ALSA, kernel `k6.12.107+deb13-amd64`; strumenti: `N/A`
- Bus: `00:03.0`; chip ID: `8086:22b8`; classe: `0480`

## Rete e servizi

### Wi-Fi

- Intel Wireless 3165, driver `iwlwifi` versione kernel
- PCIe Gen 1, 2.5 GT/s, 1 lane; bus `01:00.0`; chip ID `8086:3165`; classe `0280`
- Interfaccia `wlo1`: attiva; MAC `[REDACTED]`

### Interfacce Docker

- `br-259d784bc51c`: inattiva, MAC `[REDACTED]`
- `br-72d87e6e866f`: attiva, 10000 Mbps, duplex sconosciuto, MAC `[REDACTED]`
- `br-d986cc8017c1`: attiva, 10000 Mbps, duplex sconosciuto, MAC `[REDACTED]`
- `br-f4d2a5c9f92c`: attiva, 10000 Mbps, duplex sconosciuto, MAC `[REDACTED]`
- `docker0`: inattiva, MAC `[REDACTED]`
- `veth2512b3a`: attiva, 10000 Mbps, full duplex, MAC `[REDACTED]`
- `veth97db2a9`: attiva, 10000 Mbps, full duplex, MAC `[REDACTED]`
- `vethe6acce8`: attiva, 10000 Mbps, full duplex, MAC `[REDACTED]`

### Servizi rilevati

- `nginx`, `sshd`, `systemd-timesyncd`, `wpa_supplicant`

## Bluetooth

- Intel Bluetooth wireless interface, driver `btusb` versione `0.8`
- USB 2.0, 12 Mb/s, 1 lane, modalita 1.1
- Bus `1-4.1:4`; chip ID: `8087:0a2a`; classe `e001`
- Interfaccia rfkill `hci0`, ID `0`; stato: inattivo (`down`)
- Blocco hardware/software: no/no
- Servizio Bluetooth: non trovato; indirizzo non mostrato

## Archiviazione

- Spazio totale: `58.24 GiB`; utilizzato: `6.55 GiB` (11.2%)
- Dispositivo: `/dev/mmcblk1`; SK Hynix `HCG4a2`; tecnologia SSD rimovibile
- Major-minor: `179:0`; seriale: `[REDACTED]`; firmware: `0x8`
- Schema: GPT; blocco fisico/logico: 512/512 B
- SMART: `smartctl` non installato

### Partizioni

| Partizione | Punto di mount |         Dimensione |         Utilizzo | File system | Dispositivo      |
| ---------- | -------------- | -----------------: | ---------------: | ----------- | ---------------- |
| 1          | `/boot/efi`    | 974.1 MiB (99.80%) |     9 MiB (0.9%) | vfat        | `/dev/mmcblk1p1` |
| 2          | `/`            | 53.12 GiB (97.87%) | 6.54 GiB (12.3%) | ext4        | `/dev/mmcblk1p2` |
| 3          | swap           |           3.01 GiB |   256 KiB (0.0%) | swap        | `/dev/mmcblk1p3` |

## Memoria, swap e alimentazione

- RAM totale: 4 GiB; disponibile: 3.73 GiB; utilizzata: 2.38 GiB (63.7%)
- Memoria GPU integrata: 32 MiB
- Swap: partizione `/dev/mmcblk1p3`, 3.01 GiB, utilizzati 256 KiB (0.0%), priorita `-2`
- Swappiness: 60 (predefinito); cache pressure: 100 (predefinito); zswap: no
- Stati sospensione: `freeze`, `mem`; modalita: `s2idle`; wakeup: 0
- Ibernazione: disabilitata; immagine: 1.45 GiB

## Temperature e ventola

- CPU: 44.0 °C
- Scheda madre: non disponibile (`N/A`)
- Ventola: non disponibile (`N/A`)

## Pacchetti e strumenti

- Gestore pacchetti: `dpkg`; pacchetti: 532; librerie: 272
- Strumenti: `apt`, `apt-get`
- Compilatori rilevati: nessuno (`N/A`)
- Sudo: `1.9.16p2`; rilevazione eseguita tramite `sudo`

## Note

- `-Fxxxa` mostra informazioni complete, estese, aggiuntive e ottenute con privilegi di superutente.
- Questa rilevazione espone dati sensibili: seriali, UUID, indirizzi MAC e identificativi hardware.
- Il server grafico non è attivo nella sessione rilevata, ma il display interno e la GPU sono riconosciuti.
- Il processore era in stato di risparmio energetico a 480 MHz durante la rilevazione.
