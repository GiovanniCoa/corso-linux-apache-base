# Proxy inverso con mod_proxy

Il proxy inverso è una tecnica di networking che permette di instradare le richieste provenienti dagli utenti verso un server interno, protetto da un firewall, attraverso un server proxy esterno. In questo articolo vedremo come configurare Apache come reverse proxy utilizzando il modulo mod_proxy.

## Configurazione di Apache come proxy inverso

Per configurare Apache come reverse proxy è necessario abilitare il modulo mod_proxy. Questo modulo è già incluso nell'installazione di Apache, ma potrebbe essere necessario abilitarlo manualmente. Per farlo, è sufficiente utilizzare il comando `a2enmod proxy` seguito dal comando `service apache2 restart` per riavviare il server Apache.

Una volta abilitato il modulo mod_proxy, è possibile configurare il proxy inverso aggiungendo le seguenti direttive nel file di configurazione di Apache (solitamente `httpd.conf` o `apache2.conf`):

```
<VirtualHost *:80>
    ServerName www.example.com
    ProxyPass / http://internal-server-ip/
    ProxyPassReverse / http://internal-server-ip/
</VirtualHost>
```

In questo esempio, stiamo configurando Apache come reverse proxy per il dominio `www.example.com`, instradando tutte le richieste verso un server interno con l'indirizzo IP `internal-server-ip`. Le direttive `ProxyPass` e `ProxyPassReverse` sono utilizzate per specificare il percorso delle richieste e il server di destinazione.

## Verifica della configurazione

Una volta completata la configurazione, è possibile verificare che il proxy inverso funzioni correttamente navigando su `http://www.example.com` e verificando che le richieste vengano correttamente instradate verso il server interno.

## Conclusioni

Configurare Apache come reverse proxy utilizzando il modulo mod_proxy è un'operazione relativamente semplice che può essere utile per proteggere i server interni da attacchi esterni o per bilanciare il carico delle richieste tra diversi server. Assicurarsi sempre di configurare correttamente le regole di sicurezza e di monitorare attentamente il traffico di rete per evitare eventuali problemi di sicurezza.