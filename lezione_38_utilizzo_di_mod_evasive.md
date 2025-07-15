# Utilizzo di mod_evasive

Il mod_evasive è un modulo di sicurezza per il server Apache progettato per proteggere dai tentativi di attacchi di tipo Denial of Service (DoS) e Distributed Denial of Service (DDoS). Questi attacchi mirano a sovraccaricare il server con un elevato numero di richieste al fine di renderlo inutilizzabile per gli utenti legittimi.

## Funzionamento

Il mod_evasive funziona monitorando le richieste in arrivo al server e identificando quelle che provengono da un singolo indirizzo IP o da un range di indirizzi IP. Quando il numero di richieste supera una soglia predefinita, il modulo attiva una serie di azioni per bloccare temporaneamente l'indirizzo IP sospetto e proteggere il server da un possibile attacco.

## Configurazione

Per utilizzare mod_evasive è necessario abilitare il modulo nel file di configurazione di Apache e definire i parametri di funzionamento. È possibile impostare la soglia massima di richieste consentite entro un determinato intervallo di tempo, il tempo di blocco dell'indirizzo IP sospetto e le azioni da intraprendere in caso di superamento della soglia.

Ecco un esempio di configurazione:

```
LoadModule evasive20_module modules/mod_evasive.so

<IfModule mod_evasive20.c>
    DOSHashTableSize 3097
    DOSPageCount 2
    DOSSiteCount 50
    DOSPageInterval 1
    DOSSiteInterval 1
    DOSBlockingPeriod 10
    DOSLogDir "/var/log/httpd/"
    DOSEmailNotify admin@example.com
</IfModule>
```

In questo esempio, vengono definiti i parametri principali per il funzionamento di mod_evasive, tra cui la dimensione della tabella hash, il conteggio massimo di richieste per pagina e per sito, gli intervalli di tempo di monitoraggio, il periodo di blocco dell'indirizzo IP sospetto, la directory di log e l'indirizzo email per le notifiche.

## Conclusioni

L'utilizzo di mod_evasive è un passo fondamentale per proteggere un server Apache dagli attacchi DoS e DDoS e garantire la disponibilità dei servizi per gli utenti legittimi. Configurando correttamente il modulo e monitorando attentamente le attività sospette, è possibile prevenire efficacemente gli attacchi e mantenere la sicurezza del server.