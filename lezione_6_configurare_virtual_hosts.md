# Configurare Virtual Hosts

Quando si gestiscono più siti web su uno stesso server, è fondamentale configurare correttamente i Virtual Hosts per garantire una corretta distribuzione del traffico e una migliore gestione delle risorse. In questo articolo vedremo come configurare i Virtual Hosts su un server Apache.

## Passo 1: Creare i Virtual Hosts

Per creare un nuovo Virtual Host, è necessario creare un file di configurazione all'interno della cartella `/etc/apache2/sites-available/`. Ad esempio, se desideri creare un Virtual Host per il sito `example.com`, puoi creare un file chiamato `example.com.conf`.

```apache
<VirtualHost *:80>
    ServerAdmin webmaster@example.com
    ServerName example.com
    DocumentRoot /var/www/example.com/public_html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

## Passo 2: Abilitare i Virtual Hosts

Dopo aver creato il file di configurazione per il Virtual Host, è necessario abilitarlo eseguendo il comando:

```bash
sudo a2ensite example.com.conf
```

Questo comando creerà un link simbolico dal file di configurazione del Virtual Host alla cartella `/etc/apache2/sites-enabled/`, abilitando così il Virtual Host.

## Passo 3: Riavviare Apache

Infine, è necessario riavviare il server Apache affinché le modifiche ai Virtual Host abbiano effetto. Puoi farlo eseguendo il comando:

```bash
sudo systemctl restart apache2
```

Una volta completati questi passaggi, il Virtual Host per il sito `example.com` sarà attivo e pronto per gestire il traffico verso il sito.

## Conclusioni

Configurare i Virtual Hosts su un server Apache è un'operazione fondamentale per gestire in modo efficiente più siti web su uno stesso server. Seguendo i passaggi descritti in questo articolo, sarai in grado di creare e abilitare nuovi Virtual Hosts in modo rapido e sicuro. Ricorda sempre di riavviare Apache dopo aver apportato modifiche ai Virtual Host per assicurarti che siano correttamente configurati.