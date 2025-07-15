# Disabilitare directory listing

## Introduzione
La visualizzazione di directory senza un file index può rappresentare un potenziale rischio per la sicurezza del sito web, poiché permette agli utenti di accedere facilmente ai file presenti nella directory. Disabilitare il directory listing è quindi una pratica consigliata per proteggere i contenuti sensibili e garantire la sicurezza del sito web.

## Come disabilitare il directory listing
Esistono diverse modalità per disabilitare il directory listing, a seconda del server web utilizzato. Di seguito sono riportati i metodi per i due server web più diffusi: Apache e Nginx.

### Apache
Per disabilitare il directory listing su un server Apache, è possibile utilizzare il file `.htaccess` presente nella directory da proteggere. Aggiungere la seguente direttiva al file `.htaccess`:

```
Options -Indexes
```

Questa direttiva impedisce al server di visualizzare il contenuto della directory se non è presente un file index.

### Nginx
Nel caso di un server Nginx, è possibile disabilitare il directory listing aggiungendo la seguente direttiva al file di configurazione del server:

```
autoindex off;
```

Questa direttiva impedisce al server di visualizzare il contenuto della directory se non è presente un file index.

## Conclusioni
Disabilitare il directory listing è una pratica essenziale per garantire la sicurezza del sito web e proteggere i contenuti sensibili da potenziali attacchi. Utilizzando i metodi descritti sopra è possibile impedire la visualizzazione delle directory senza un file index, riducendo così i rischi legati alla sicurezza del sito web.