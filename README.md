# Server-Portatile-HP

Documentazione tecnica e portfolio del mio home lab realizzato su un portatile HP.

Il progetto raccoglie configurazione, motivazioni tecniche, procedure operative e
progressi nella gestione di un piccolo server Linux. L’obiettivo è documentare un
ambiente reale, riproducibile e mantenibile, non soltanto elencare i container attivi.

## Obiettivi del laboratorio

- amministrare un host Debian con risorse limitate;
- pubblicare servizi in modo controllato e con accesso remoto tramite VPN;
- gestire DNS, reverse proxy, certificati TLS e aggiornamenti dei container;
- applicare una separazione chiara tra configurazione versionata, segreti e dati persistenti;
- annotare decisioni, problemi riscontrati e procedure di manutenzione.

## Ambiente

Il server è un portatile HP con processore Intel Atom x5-Z8350, 4 GiB di RAM e
storage eMMC. I dettagli hardware, software e le ottimizzazioni energetiche sono
disponibili in [Server HP Info.md](Server%20HP%20Info.md) e
[Ottimizzazione batteria.md](Batteria/Ottimizzazione%20batteria.md).

## Container Docker

Ogni servizio ha una cartella autonoma con il proprio `docker-compose.yml`:

| Servizio            | Scopo                                  | Cartella                  |
| ------------------- | -------------------------------------- | ------------------------- |
| AdGuard Home        | DNS locale e filtraggio                | [AdGuard](AdGuard/)       |
| DuckDNS             | Aggiornamento del record DNS dinamico  | [Duckdns](Duckdns/)       |
| Nginx Proxy Manager | Reverse proxy e certificati TLS        | [npm](npm/)               |
| wg-easy             | VPN WireGuard e gestione dei client    | [vpn](vpn/)               |
| Watchtower          | Aggiornamento e pulizia delle immagini | [WatchTower](WatchTower/) |

Il flusso previsto è: risoluzione del nome pubblico tramite DuckDNS, ingresso
controllato dal reverse proxy o dalla VPN, quindi instradamento verso i servizi
interni. Le porte e gli indirizzi effettivi dipendono dalla rete locale e non sono
inclusi nella documentazione pubblica.

## Sicurezza e privacy

I file `.env` e i dati persistenti dei container sono esclusi da Git tramite
[.gitignore](.gitignore). Non inserire mai token, password, hash, domini personali,
indirizzi IP pubblici o chiavi private nei compose versionati.

Prima di pubblicare nuove informazioni, controllare anche log, screenshot, export di
configurazione e documentazione hardware: seriali, UUID, indirizzi MAC e identificativi
del dispositivo devono essere rimossi o sostituiti con placeholder.

## Competenze documentate

Questo repository è strutturato per dimostrare competenze pratiche nelle seguenti aree:

- **Amministrazione Linux:** Gestione di un host Debian, ottimizzazione delle risorse su hardware limitato e manutenzione di un sistema a basso consumo.
- **Containerizzazione:** Deploy, aggiornamento e gestione di servizi tramite Docker e Docker Compose (es. Watchtower).
- **Networking e Accessi:** Configurazione di tunnel VPN (WireGuard) per l'accesso remoto sicuro, gestione del DNS locale e filtraggio (AdGuard Home) e configurazione di DNS dinamico (DuckDNS).
- **Gestione Traffico Web:** Configurazione di Reverse Proxy (Nginx Proxy Manager) e gestione automatizzata dei certificati TLS.
- **Security Best Practices:** Separazione netta tra configurazione versionata e segreti (`.env`), esclusione dei dati sensibili e backup dei dati persistenti.

## Metodo di Lavoro

Le nuove attività e le modifiche al server vengono documentate seguendo questo schema strutturato:

*   **Problema:** Il problema o la necessità tecnica affrontata.
*   **Soluzione:** La configurazione o l'architettura adottata per risolvere il caso.
*   **Azione:** Il comando esatto eseguito.
*   **Verifica:** Il modo in cui la soluzione è stata testata e confermata.