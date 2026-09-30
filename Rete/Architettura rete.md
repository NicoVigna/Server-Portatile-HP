# Architettura di rete

## Connettivita del server

Il server HP usa Debian ed e collegato alla rete locale tramite Ethernet. Il
suo indirizzo locale e riservato nella configurazione della rete.

La connessione Internet e fornita da TIM FWA ed e soggetta a CGNAT. Di
conseguenza non sono previsti port forwarding o accessi diretti dall'esterno.

## Servizi locali

AdGuard Home gestisce centralmente:

- assegnazione degli indirizzi IP tramite DHCP;
- risoluzione DNS per i dispositivi della rete;
- filtraggio delle richieste;
- inoltro verso upstream cifrati tramite DoH e DoT, con richieste parallele.

Una regola DNS locale wildcard inoltra `*.vignali.me` verso l'indirizzo locale
del server e consente ai dispositivi interni di risolvere i sottodomini senza
uscire su Internet.

Nginx Proxy Manager riceve le richieste Web dalla rete locale e le inoltra ai
servizi interni in base al sottodominio richiesto, ad esempio le interfacce di
Immich o AdGuard. Il certificato wildcard Let's Encrypt e stato ottenuto con
una DNS Challenge Cloudflare, usando un token API con il solo permesso di
modifica della zona DNS. Il token e configurato fuori dal repository.

## Componenti non utilizzati

DuckDNS e conservato nella cartella dedicata solo come riferimento storico e
non viene avviato. Il tunnel Cloudflare Zero Trust e stato testato e poi
smantellato; non e presente nello stack attivo.

## Manutenzione

Watchtower controlla gli aggiornamenti ogni notte alle 04:00, rimuove le
vecchie immagini dopo l'aggiornamento e usa `DOCKER_API_VERSION=1.40` per la
compatibilita con il demone Docker installato.
