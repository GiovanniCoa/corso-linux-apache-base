# Configurazione base di un Virtual Host

Nella gestione di un server web, la configurazione dei Virtual Host è un elemento fondamentale per poter ospitare più siti web su un unico server fisico. In questo articolo, verrà fornita una guida dettagliata sulla configurazione base di un Virtual Host, con particolare attenzione ai file di configurazione e ai parametri fondamentali da definire.

## File di configurazione

I Virtual Host sono definiti all'interno dei file di configurazione del server web. Per esempio, nel caso di Apache, i file di configurazione dei Virtual Host si trovano nella directory `/etc/apache2/sites-available/` (su sistemi basati su Debian/Ubuntu) o `/etc/httpd/conf.d/` (su sistemi basati su CentOS/RHEL).

All'interno di questi file, è possibile definire le direttive necessarie per configurare il Virtual Host, come ad esempio il nome del dominio, il percorso della root del sito, le regole di reindirizzamento, e così via.

## Parametri fondamentali

I parametri fondamentali da definire all'interno del file di configurazione di un Virtual Host includono:

- `ServerName`: specifica il nome del dominio associato al Virtual Host
- `DocumentRoot`: specifica il percorso della directory radice del sito web
- `ErrorLog` e `CustomLog`: specificano i percorsi dei file di log di errore e di accesso
- `Directory`: permette di definire le regole di accesso alla directory specificata
- `Alias`: permette di creare un alias per un percorso specifico

## Esempio di configurazione

Di seguito è riportato un esempio di configurazione di un Virtual Host per un sito web chiamato `example.com`:

```apache
<VirtualHost *:80>
    ServerName example.com
    DocumentRoot /var/www/example.com/public_html
    ErrorLog /var/log/apache2/example.com_error.log
    CustomLog /var/log/apache2/example.com_access.log combined

    <Directory /var/www/example.com/public_html>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```

In questo esempio, il Virtual Host è configurato per rispondere alle richieste per il dominio `example.com`, utilizzando la directory `/var/www/example.com/public_html` come root del sito web e salvando i log di errore e di accesso nei percorsi specificati.

## Conclusione

La corretta configurazione dei Virtual Host è essenziale per garantire il corretto funzionamento e la sicurezza dei siti web ospitati su un server. Seguendo le linee guida e i parametri fondamentali descritti in questo articolo, è possibile creare e gestire efficacemente i Virtual Host per ospitare più siti web su un unico server fisico.