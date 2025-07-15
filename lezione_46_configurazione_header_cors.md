# Configurazione header CORS

Il Cross-Origin Resource Sharing (CORS) è un meccanismo di sicurezza implementato dai browser web per impedire richieste di risorse da domini diversi. Questo meccanismo può essere gestito tramite la configurazione degli header CORS sul server.

## Cosa sono gli header CORS

Gli header CORS sono informazioni aggiuntive che vengono inviate dal server al browser per indicare se una determinata risorsa può essere condivisa con un altro dominio. Questi header includono informazioni come l'origine della richiesta, i metodi HTTP consentiti e i tipi di header accettati.

## Come configurare gli header CORS

Per configurare gli header CORS sul server, è necessario modificare le impostazioni del server web o del framework utilizzato per gestire le richieste HTTP. È possibile specificare le regole CORS attraverso l'aggiunta di appositi header nella risposta HTTP inviata dal server.

Ecco un esempio di come configurare gli header CORS utilizzando Apache:

```apache
Header set Access-Control-Allow-Origin "*"
Header set Access-Control-Allow-Methods "GET, POST, OPTIONS"
Header set Access-Control-Allow-Headers "Content-Type"
```

In questo esempio, stiamo consentendo a tutti i domini di accedere alle risorse del server, specificando i metodi HTTP consentiti (GET, POST, OPTIONS) e i tipi di header accettati (Content-Type).

## Conclusioni

La corretta configurazione degli header CORS è essenziale per consentire la condivisione di risorse tra domini diversi in modo sicuro e controllato. Assicurati di configurare correttamente gli header CORS sul tuo server per garantire la sicurezza e l'accessibilità delle tue risorse da parte di altri domini.